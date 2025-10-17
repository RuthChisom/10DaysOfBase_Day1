## Foundry

**Foundry is a blazing fast, portable and modular toolkit for Ethereum application development written in Rust.**

Foundry consists of:

-   **Forge**: Ethereum testing framework (like Truffle, Hardhat and DappTools).
-   **Cast**: Swiss army knife for interacting with EVM smart contracts, sending transactions and getting chain data.
-   **Anvil**: Local Ethereum node, akin to Ganache, Hardhat Network.
-   **Chisel**: Fast, utilitarian, and verbose solidity REPL.

## Documentation

https://book.getfoundry.sh/

## Usage

### Build

```shell
$ forge build
```

### Test

```shell
$ forge test
```

### Format

```shell
$ forge fmt
```

### Gas Snapshots

```shell
$ forge snapshot
```

### Anvil

```shell
$ anvil
```

### Deploy

```shell
$ forge script script/Counter.s.sol:CounterScript --rpc-url <your_rpc_url> --private-key <your_private_key>
```

### Cast

```shell
$ cast <subcommand>
```

### Help

```shell
$ forge --help
$ anvil --help
$ cast --help
```

```
BASE_SEPOLIA_RPC_URL : https://dashboard.alchemy.com/apps/
```
ETHERSCAN_API : https://etherscan.io/apidashboard
```
Base Sepolia testnet : https://console.optimism.io/faucet
```
DEPLOY
```

forge create "src/Greeting.sol:Greeter" --rpc-url "$BASE_SEPOLIA_RPC_URL" --broadcast --private-key "$PRIVATE_KEY" --constructor-args "Hello Base Builders"

VERIFY

forge verify-contract --chain base-sepolia "0x81AeC0B87CAa631365B0AC0B628A84afdf6f1Fe9" "src/Greeting.sol:Greeter" --verifier etherscan --etherscan-api-key "$ETHERSCAN_API" --constructor-args "$(cast abi-encode 'constructor(string)' 'Hello Builders')"