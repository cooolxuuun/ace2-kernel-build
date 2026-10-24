# ace2-kernel-build

OnePlus Ace 2 (PHK110, SM8475 / waipio) kernel built on GitHub Actions,
with Droidspaces support.

- Phone: PHK110_16.0.5.1201(CN01), Android 16, kernel 5.10.236-android12-9 (KMI 5.10-android12-9)
- Source: OnePlusOSS/kernel_manifest, branch `oneplus/sm8475`, manifest `oneplus_ace2_b.xml`
  (kernel projects at `oneplus/sm8475_b_16.0.0_ace_2`)
- Workflow: `.github/workflows/build-ace2-kernel.yml` (workflow_dispatch only)
  - `build_mode`: `baseline` (unmodified source) or `droidspaces` (+ kABI patches + GKI defconfig)
  - `kabi_patch_variant`: `6_7_8` (default), `3_4_5`, `1_2_3`
  - `integrate_ksu`: false by default (recommended: install KernelSU in LKM mode after booting this kernel)

Do not flash any artifact blindly: back up the stock boot.img first and
prefer `fastboot boot <new boot.img>` for a temporary test.
