# DEPRECATED

use [debian-dev](../debian-dev)

> Due to [the relicensing of HashiCorp software](https://www.hashicorp.com/blog/hashicorp-adopts-business-source-license) to [BUSL-1.1](https://spdx.org/licenses/BUSL-1.1.html), a non-Open-Source license, the following software has been removed from Alpine:
> 
> Consul
> Nomad
> Packer
> Terraform
> Vault
>
> Our discussion on the topic can be found [here](https://gitlab.alpinelinux.org/alpine/aports/-/issues/15193).

\- https://wiki.alpinelinux.org/wiki/Release_Notes_for_Alpine_3.19.0

---

In development we've started using [Nx](https://nx.dev).

Nx has the [concept of _affected_](https://nx.dev/latest/node/core-concepts/affected#affected), as in `yarn nx affected:test` or `yarn nx affected:lint`, this uses git to determine differences to a git branch (defaulted to `master`). These [_affected_ commands](https://nx.dev/latest/node/cli/affected) fail when using our default base image because git is not installed.