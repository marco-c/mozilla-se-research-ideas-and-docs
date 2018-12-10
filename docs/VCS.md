## Mercurial and Git
Firefox is in a mercurial repository, but there are git clones too.
The main repositories are:
- <https://hg.mozilla.org/mozilla-central/> is the Mercurial repository which contains the code for the Nightly version of Firefox.
- <https://hg.mozilla.org/releases/mozilla-beta/> is the Mercurial repository for the Beta version of Firefox.
- <https://hg.mozilla.org/releases/mozilla-release/> is the Mercurial repository for the Release version of Firefox.
- <https://github.com/mozilla/gecko-dev> is the official git mirror for mozilla-central.

## Integration branches
Patches are usually landed first on integration branches (<https://hg.mozilla.org/integration/mozilla-inbound> or <https://hg.mozilla.org/integration/autoland>). Patches are rebased on top of the integration branch before being landed. Inbound is used by developers manually. Autoland is used by automated tools to land patches from a queue of landable patches (e.g. from MozReview or from Phabricator). Periodically, a few times a day, code from inbound or autoland is merged to the mozilla-central branch. The same happens on the opposite direction (code from mozilla-central is merged to inbound and autoland).
More documentation at \[1\].

## Link between commits and bugs
Almost any commit is linked to a bug on Bugzilla, and the link is pretty clear (see following section).

## Commit message format
Almost all commits are in the following format:
```
Bug XXX - SHORT DESCRIPTION. r=FIRST_REVIEWER,SECOND_REVIEWER

LONG DESCRIPTION (optional).
```

XXX is the bug number on Bugzilla.
r= is used to note who reviewed the patch. The names are often the IRC nicknames of developers.
sr= is used when there are super-reviews (very rarely now).
a= is used when a patch has been uplifted to note who approved the patch.

## Link between VCS users and Bugzilla users
The link is not perfect unfortunately. E.g. it's not straightforward to go from one of the reviewers in the "r=" list and the users on Bugzilla. Also, users change names and email addresses from time to time, which makes the mapping harder.
There is a .mailmap file \[2\] that might alleviate this problem somehow, but it is still not used so much.

\[1\]: <https://wiki.mozilla.org/Tree_Rules>
\[2\]: <https://hg.mozilla.org/mozilla-central/file/tip/.mailmap>
