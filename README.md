# CoreShift-GKI

This branch is a minimal CoreShift-GKI consumer branch.

Kernel source and build control come from `CoreShiftD/android_kernel_common_lts`. This repository only selects the ACK profile branch, consumes that repository's JSON profile, runs its build wrapper, and uploads the produced output.

The GitHub Actions ACK wrapper step opts into `DISABLE_DEFCONFIG_CHECK=1` as a
CI escape hatch for legacy `google_build_sh` `savedefconfig` enforcement. That
override lives in CI only; it is not enabled by default in
`android_kernel_common_lts`.

Artifact staging also makes a best-effort attempt to extract embedded IKCONFIG
into `dist/config/ikconfig-extracted.config` using
`kernel/common/scripts/extract-ikconfig`. Extraction is non-fatal and only
works when the built kernel image includes `CONFIG_IKCONFIG`.

There is no patch system, release system, SUSFS integration, BBG integration, manager integration, repo sync, or local build system yet.
