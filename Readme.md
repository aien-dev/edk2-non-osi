> **AIEN fork.** This is the AIEN copy of [tianocore/edk2-non-osi](https://github.com/tianocore/edk2-non-osi). AIEN keeps it because it is one of the four sources the Raspberry Pi 5 UEFI firmware is built from (see [aien-dev/rpi5-uefi](https://github.com/aien-dev/rpi5-uefi)), so that build keeps working if the original moves or disappears. The `master` branch matches upstream apart from this note; AIEN carries no code changes here. Status (2026-10-18): in step with upstream `master` (last upstream change 2026-04-02). AIEN itself starts at [Aienix](https://github.com/aien-dev/aienix), the core tree of AIEN.
>
> Everything below this note is the upstream README, unchanged.

This branch holds modules not compatible with the normal
[edk2](https://github.com/tianocore/edk2) and
[edk2-platforms](https://github.com/tianocore/edk2-platforms)
licensing requirements, and any associated files.

As such, this repository has no top-level License.txt, and each module (or
group of modules) must provide their own License.txt. Where any conflict exists,
the License.txt nearest to the module in simple hierarchy takes precedence.
That is, `Vendor/Module/License.txt` would take precedence over
`Vendor/License.txt` for `Vendor/Module/Module.efi`.
