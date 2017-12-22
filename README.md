This repository contains the CoreOS branches of Linux. A new branch is created for each kernel version the distribution is rebased onto. The currently shipped version is available in the [overlay repository](https://github.com/coreos/coreos-overlay/tree/master/sys-kernel/coreos-sources/files).

This repository is not used by the build process at all; it merely exists for generating patchsets that live in coreos-overlay. To add a patch, check out the branch you want to add a patch to (probably v${VERSION}-coreos), apply the patch, then run `git format-patch ${TAG}` where tag is the upstream kernel tag (no "-coreos"). This generates a set of patches that can be used by `./revbump.sh` script in the `coreos-sources` directory in the overlay.

```sh
git checkout v4.13.16-coreos

<Apply and commit your patch>

git format-patch v4.13.16
# check that the patches were generated correctly
ls *.patch
```
