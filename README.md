# SubNav: The Subnet Navigator

The Subnet Navigator (SubNav) is a tool to bring together [Subnet](https://support.avax.network/en/articles/4064861-what-is-a-subnet) builders and Avalanche [Validators](https://support.avax.network/en/articles/4064704-what-is-a-blockchain-validator).

**Note:** This project was built over a weekend as part of the [Avalanche Summit Hackathon](https://hackathon.avalanchesummit.com/).

## Features

**Anyone** can use SubNav to list Subnets, Blockchains and Validators.

A **Subnet owner** can claim a Subnet as his in SubNav and enrich its listing with informations about it. These metadatas are stored on-chain in a special Subnet running an instance of an [Subnet EVM](https://github.com/ava-labs/subnet-evm).

An **Avalanche validator** can list the existing subnets, see their validating nodes and what blockchains the subnets are running. The metadatas added by the Subnet owner will help any validators to have a better view of what each subnet is for.

## Architecture

## Repositories

The SubNav source code is composed of multiple repositories: 

- [contracts](https://github.com/Avackathon/contracts): Solidity contracts backing the SubNav project.
- [frontend](https://github.com/Avackathon/frontend): React WebApp of the SubNav project.
- [infra](https://github.com/Avackathon/infra): Ansible environment used to manage the Fuji validator, Fuji subnet and EVM blockchain backing the SubNav project.
- [faucet](https://github.com/Avackathon/faucet): Simple FastAPI Python backend to quickly fund wallets with `$SUB` tokens, the native token of the SubNav subnet.

