## Socorro
Socorro is the server component in the Mozilla's automated crash reporting system.

## Signature
The "Signature" is the name assigned to a set of crashes. Developers (and me in this document) may refer to groups of crashes with the word "group" or with the word "signature" or with the word "cluster". Often developers also use the singular "top crasher" to refer to the group of crashes.

The signature generation is partially documented at \[1\], and its source code can be found at \[2\].

Given that the clustering algorithm is not great, a bug on Bugzilla can be linked to one or more signatures (if the group contains unrelated crashes, the bug will be linked to more than one signature). One signature can be linked to multiple crashes (if the group contains unrelated crashes, multiple bugs might be linked to the same signature.
Not all signatures have a bug linked to them (indeed, there are, at the time of writing, more than 200'000 clusters, but Mozilla only cares about the top clusters, since the first 200 contain ~55% of the crashes \[3\]).

Let's see two examples:

- Two crashes might be completely unrelated from each other but might be happening in the same function (very frequent with JS engine crashes), the signature will contain both crashes. Two bugs will likely be filed with the same signature. In reality, it's possible that one of the crashes will be missed, at least at first until one of them is fixed, given that they are all lumped together.

- Two crashes might have the same root cause but might be happening in different functions (e.g. a crash in a gfx driver caused by wrong usage of some gfx API might have the top function depend on the gfx driver being used). One bug will be filed with two signatures. In reality, multiple bugs will be filed, one for each signature. In the best case developers notice the crash is the same and the bugs will all be duplicated; in the worst case one bug will be fixed and the others will be ignored as the numbers of crashes will decrease to 0.

## Seemingly garbled function names
When there are memory addresses instead of a function, it means that for some reason the debugging information could not be used to symbolicate the raw crash dump. It could be one of several reasons:
1. generated code (the JavaScript JIT engine compiles JavaScript code on the fly and puts executable code somewhere in memory, if there's a crash in the generated code there is not going to be a function name);
2. crashes that make the program jump to a random address in memory (there are a few of those).
There are also cases of functions which could not be symbolicated because Mozilla did not have the debugging symbols (e.g. a third-party DLL, like an antivirus), in these cases you will see things like "thirdparty.dll@0xADDRESS". For Flash plugin crashes instead, the function name might seem meaningless (e.g. "F1398665248_____________________________"), but it is actually a proper name, just obfuscated by Adobe.

\[1\]: <https://socorro.readthedocs.io/en/latest/signaturegeneration.html>  
\[2\]: <https://github.com/mozilla-services/socorro/tree/4fea1a63f8a8c39d4c81717a9c156ab06ceff600/socorro/signature>  
\[3\]: Marco Castelluccio, Carlo Sansone, Luisa Verdoliva, and Giovanni Poggi - Automatically analyzing groups of crashes for finding correlations. In Proceedings of the 2017 11th Joint Meeting on Foundations of Software Engineering (ESEC/FSE), 2017, pages 717-726.
