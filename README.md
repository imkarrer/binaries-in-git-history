# binaries-in-git-history
Demonstrates what happens when git is asked to track binary files

For each command we will inspect the current size of the repository and discuss what happened.

Each time we snapshot the size of the repository we will have run `git gc` to force git to condense everything to a .pack file


A freshly initialized repository is only 64k
```
$ du -sch .[!.]* *
 64K    .git
```

When we add the readme nothing changes in `.git`, nor will it until the file is tracked via `add`
```
$ du -sch .[!.]* *
 64K    .git
  0B    README.md
 64K    total
```

But once we track it and add content...

Note: For those keeping score an additional commit will be made to log the size after `git gc` has executed.
