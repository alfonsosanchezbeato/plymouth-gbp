# Introduction

This repository contains the plymouth Ubuntu package plus some changes
developed for the Ubuntu Core splash. As this is a non-native debian
package, we will use gbp to handle in a clean way the patches on top
of the release tarball.

The package was imported by running
```
$ apt source plymouth
$ gbp import-dsc --pristine-tar plymouth_*.dsc
```

# Developing

To apply the existing patches, run
```
$ gbp pq import
```

After doing some changes and commiting them, the changes can be
exported as debian patches with

```
$ gbp pq export
```

That will create one patch per commit. Those changes can be commited
and then proposed as a PR to this repo. Make sure to edit
appropriately the debian changelog before doing so.

# Building

To build the debian packages, run
```
gbp buildpackage --git-ignore-branch -us -uc
```
