- Git is distributed. Remote repo == local repo
- All info is kept in `.git/`, what you see is a checked out version of what's inside that directory. This representation is called work tree.
- Commit is just a file, here is its content: `git cat-file -p HEAD`.
 - It has a parent commit which is just a previous commit
 - Any commit is a reference to the root `tree` (directory)
- Any tree is a file: `git cat-file -p HEAD^{tree}`. Trees represent directories. They respectively contain other trees and files. 
- All the commit, tree and blob objects are kept inside of `.git/objects` directory.

- Git branch is just a pointer (reference) to a Git commit. 
- Without branches you'd need to work with commit hashes directly exchanging with your co-workers with sha1 hashes (e56ccc0d224de014f067438effb7139dc3f78a9a).
- Your local branches can be found under `.git/refs/heads` - take a look what's inside of those files - just references to the commits.
- Other types of refs:
 - Tags - is a static link to a commit. It's like a way to bookmark some important commits.
 - HEAD - is a reference to a commit that's currently checked out.
 - Annotated Tags - static references like usual tags, but it's not inside of `.git/refs/tags` but in `.git/objects` and therefore it keeps information on when it was created and who did that.

