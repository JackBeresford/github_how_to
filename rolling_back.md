# Rolling back

Using git we can restore files that were accidentally deleted or changed for the worse.

The techniques differ in how far gone we are in the commit process

## Before adding files to the staging area (git add)

```
git checkout HEAD .
```

## After adding files, but before committing them

```
git reset HEAD .
git checkout HEAD .
```

## After commiting files

```
git log --oneline
> # note the SHA (first numbers) of the commit BEFORE the commit made in error
> # i.e. the 2nd most recent
git reset <SHA>
git checkout HEAD .
```

## With a remote origin

Note that we have fixed our local git repo here, but may still be mismatched with the remote repo.
Therefore try these:

```
git pull origin main
git revert <sha_of_mistake>
git push origin main
```

