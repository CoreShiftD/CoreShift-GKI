# CoreShift-GKI

This branch is a minimal CoreShift-GKI consumer branch.

Kernel source and build control come from `CoreShiftD/android_kernel_common_lts`. This repository only selects the ACK profile branch, consumes that repository's JSON profile, runs its build wrapper, and uploads the produced output.

There is no patch system, release system, SUSFS integration, BBG integration, manager integration, repo sync, or local build system yet.
