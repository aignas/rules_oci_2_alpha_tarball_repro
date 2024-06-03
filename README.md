# A small repro to try and verify the tarball failure

This fails with:
```console
$ bazel build :tarball_filegroup
INFO: Analyzed target //:tarball_filegroup (82 packages loaded, 788 targets configured).
ERROR: /Users/ignas.anikevicius/src/github/aignas/rules_oci_2_alpha_tarball_repro/BUILD.bazel:18:12: OCITarball tarball/tarball.tar failed: (Exit 1): tar failed: error executing OCITarball command (from target //:tarball) external/aspect_bazel_lib~~toolchains~bsd_tar_darwin_amd64/tar --create --no-xattr --no-mac-metadata --cd bazel-out/darwin_x86_64-fastbuild/bin --file ... (remaining 2 arguments skipped)

Use --sandbox_debug to see verbose messages from the sandbox and retain the sandbox build root for debugging
tar: Error reading archive ../../../bazel-out/darwin_x86_64-fastbuild/bin/tarball/tarball.spec: Can't open bazel-out/darwin_x86_64-fastbuild-ST-a5417e5bb688/bin/external/rules_oci~~oci~alpine_linux_amd64/layout/blobs/sha256/05455a08881ea9cf0e752bc48e61bbd71a34c029bb13df01e40e3e70e0d007bd
tar: Error exit delayed from previous errors.
Target //:tarball_filegroup failed to build
Use --verbose_failures to see the command lines of failed build steps.
INFO: Elapsed time: 9.920s, Critical Path: 1.19s
INFO: 8 processes: 6 internal, 1 darwin-sandbox, 1 local.
ERROR: Build did NOT complete successfully
```
