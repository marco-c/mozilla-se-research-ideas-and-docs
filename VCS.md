## Mercurial and Git
Firefox is in a mercurial repository, but there are git clones too.
The main repositories are:
- <https://hg.mozilla.org/mozilla-central/> is the Mercurial repository which contains the code for the Nightly version of Firefox.
- <https://hg.mozilla.org/releases/mozilla-beta/> is the Mercurial repository for the Beta version of Firefox.
- <https://hg.mozilla.org/releases/mozilla-release/> is the Mercurial repository for the Release version of Firefox.
- <https://github.com/mozilla/gecko-dev> is the official git mirror for mozilla-central.

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
There is a .mailmap file that might alleviate this problem somehow, but it is still not used so much: <https://hg.mozilla.org/mozilla-central/file/tip/.mailmap>.
