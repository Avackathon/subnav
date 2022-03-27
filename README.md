# SubNav: The Subnet Navigator

The Subnet Navigator (SubNav) is a tool to bring together [Subnet](https://support.avax.network/en/articles/4064861-what-is-a-subnet) builders and Avalanche [Validators](https://support.avax.network/en/articles/4064704-what-is-a-blockchain-validator).

SubNav is available on the Fuji network at https://subnav.network.

**Note:** This project was built over a weekend as part of the [Avalanche Summit Hackathon](https://hackathon.avalanchesummit.com/).

## Features

**Anyone** can use SubNav to list Subnets, Blockchains and Validators.

A **Subnet owner** can claim a Subnet as his in SubNav and enrich its listing with informations about it. These metadatas are stored on-chain in a [smart contract](https://github.com/Avackathon/contracts/blob/master/contracts/SubNav.sol). This smart contract lives in a special Subnet called the **SubNav network** running an instance of an [Subnet EVM](https://github.com/ava-labs/subnet-evm).

An **Avalanche validator** can list the existing subnets, see their validating nodes and what blockchains the subnets are hosting. The metadatas added by the Subnet owner will help any validators to have a better view of what each subnet is for, how to join as a validator, if there are incentives, etc.

## Architecture

## SubNav Subnet

The **SubNav Subnet** is a Fuji network subnet validated by `NodeID-Czk2sjkBvgjf9wwqQoFUurVYbDgpcTAKo` created for the purpose of the SubNav project.

## SubNav EVM

The **SubNav EVM** is a blockchain running on the **SubNav Subnet**. It is an instance of the [Subnet EVM](https://github.com/ava-labs/subnet-evm) and is available at the following RPC:

```
url: "https://fuji.subnav.network/ext/bc/subnav/rpc"
chainId: 13213
```

## SubNav contract

The SubNav contract is a Solidity smart contract deployed on the **SubNav EVM**. It is used to store metadatas about the subnets and their owners.

## Repositories

The SubNav source code is composed of multiple repositories: 

- [contracts](https://github.com/Avackathon/contracts): Solidity contracts backing the SubNav project.
- [frontend](https://github.com/Avackathon/frontend): React WebApp of the SubNav project.
- [infra](https://github.com/Avackathon/infra): Ansible environment used to manage the Fuji validator, Fuji subnet and EVM blockchain backing the SubNav project.
- [faucet](https://github.com/Avackathon/faucet): Simple FastAPI Python backend to quickly fund wallets with `$SUB` tokens, the native token of the SubNav subnet.
- [notification-service](https://github.com/Avackathon/notification-service/): A Python script to alert Subnet owners and Validators when their validating periods approach the end.

## TODO

There are still some features we did not have the time to implement:

- The SubNav frontend currently only lists Subnets, we would like to implement lists of Validators and VMs next.
- The notification service does not email users yet, it only lists the leasing periods.
- The notification service should only apply to subnets and users that are registered on SubNav.
