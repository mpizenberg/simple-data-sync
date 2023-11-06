# Simple Data Sync

The goal of this project is to provide a simple user-friendly data
synchronisation tool. This should be especially useful for storing datasets of
images and other medium size files.

DVC has some issues, including:

- Data is duplicated with cache on NTFS external disks (no good for Windows),
  doubling the dataset size
- It is rather slow compared to raw sync with remote storage
- It tries to do too many things, making the tool more complex than necessary
- There are some bugs with git-ignored directories

Since we are starting from scratch, we can also imagine new user-friendly ways
of identifying data to be synced. One of the ideas I have is to get rid of the
interaction with `*.dvc` files via a command line utility. Instead of `dvc add`,
`dvc push`, `dvc pull`, and many other commands, identification of synced filed
is done in a simple markdown file.

```md
- [x] data_a/
- [ ] data_b/
<!-- - [ ] untracked.png -->
- [x] img_0.jpg
```

The nice thing is that in an editor able to render markdown files, it renders
like this directly.

- [x] data_a/
- [ ] data_b/
<!-- - [ ] untracked.png -->
- [x] img_0.jpg
