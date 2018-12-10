Some parts of Firefox are developed in GitHub, with different practices than the usual ones on Bugzilla. The code lives both in the canonical mozilla-central repository and in project-specific GitHub repositories (for example, the new tab page \[1\] or the PDF reader \[2\]). Depending on the project, bugs might live in Bugzilla, in GitHub issues, or in both.
Periodically, or when needed, the project-specific code from GitHub is updated in mozilla-central. This situation is currently still not great because of the different processes adopted by different projects. Also, this situation makes it hard for release managers to figure out exactly what bugs there are and what is being changed (since the updates from the GitHub projects to mozilla-central are often big, lumping together multiple patches, and not really reviewable). See also \[3\], whose linked bugs show a few of the problems with the integration of two bug tracking systems.

\[1\]: <https://github.com/mozilla/activity-stream>  
\[2\]: <https://github.com/mozilla/pdf.js>  
\[3\]: <https://bugzilla.mozilla.org/show_bug.cgi?id=1496895>
