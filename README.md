[![ci](https://github.com/tillitis/tkeysign/actions/workflows/ci.yaml/badge.svg?branch=main&event=push)](https://github.com/tillitis/tkeysign/actions/workflows/ci.yaml) [![Go Reference](https://pkg.go.dev/badge/github.com/tillitis/tkeysign.svg)](https://pkg.go.dev/github.com/tillitis/tkey-pq-device-sign)

# Tillitis tkey-pq-device-sign package

> ℹ️  This branch is for demo purpose.
>
> **`castor-support-demo` branch:** adds `Signer.SendReset` and
> `ResetType` (`ResetTypeStartClient`, `ResetTypeStartDefault`), used
> to reclaim a Castor TKey from another resident app (e.g.
> `tkey-fido2`) before loading the signer, and to hand it back to its
> default boot path afterwards.
>
> No special build steps beyond the usual `go build`. To see this used
> end to end, check out the `castor-support-demo` branch of
> `tkey-pq-sign-cli` (which imports this package as a sibling repo via
> its `go.mod` `replace` directive) and, to also support resetting the
> signer app itself, of `tkey-pq-device-signer` (requires tkey-libs
> `TK1-Q-beta-1`); test against a real Castor TKey or the `tk1-castor`
> QEMU machine.
A Go package for communicating with the [`tkey-pq-device-signer` device
app](https://github.com/tillitis/tkey-pq-device-signer) on a
[Tillitis](https://tillitis.se/) TKey to get cryptographic signatures
over a message.

The package has functionality to call for signing with external MU
computation, the external is used by the `tkey-pq-device-signer`
uses external computation for signing.

See the [ML-DSA
draft](https://www.ietf.org/archive/id/draft-connolly-cfrg-ml-dsa-security-considerations-01.html#name-external-mu)
for more info about external MU computation.

See the [Go doc](https://pkg.go.dev/github.com/tillitis/tkey-pq-device-sign)
for `tkey-pq-device-sign` for details on how to call the functions.

See [tkey-pq-sign-cli](https://github.com/tillitis/tkey-pq-sign-cli) for client
applications using this go package.

Release notes in [RELEASE.md](RELEASE.md).

## Licenses and SPDX tags

Unless otherwise noted, the project sources are copyright Tillitis AB,
licensed under the terms and conditions of the "BSD-2-Clause" license.
See [LICENSE](LICENSE) for the full license text.

Until Oct 25, 2024, the license was GPL-2.0 Only.

External source code we have imported are isolated in their own
directories. They may be released under other licenses. This is noted
with a similar `LICENSE` file in every directory containing imported
sources.

The project uses single-line references to Unique License Identifiers
as defined by the Linux Foundation's [SPDX project](https://spdx.org/)
on its own source files, but not necessarily imported files. The line
in each individual source file identifies the license applicable to
that file.

The current set of valid, predefined SPDX identifiers can be found on
the SPDX License List at:

[https://spdx.org/licenses/](https://spdx.org/licenses/)

We attempt to follow the [REUSE
specification](https://reuse.software/).
