# Uniswap v3

This doc aims to document how to access all values exposed to end users in the Uniswap v3 interface. The assumption is that users are interacting with `web3.py` but this should work for all other related libraries.

## Main contracts

| Contract name                | Address                                      | ABI                                                          |
| ---------------------------- | -------------------------------------------- | ------------------------------------------------------------ |
| `NonfungiblePositionManager` | `0xC36442b4a4522E871399CD717aBDD847Ab11FE88` | [link](http://api.etherscan.io/api?module=contract&action=getabi&address=0xc36442b4a4522e871399cd717abdd847ab11fe88&format=raw) |
| `UniswapV3Factory`           | `0x1F98431c8aD98523631AE4a59f267346ea31F984` | [link](http://api.etherscan.io/api?module=contract&action=getabi&address=0x1F98431c8aD98523631AE4a59f267346ea31F984&format=raw) |
| `UniswapV3Pool`              | Varies based on pool                         | [link](http://api.etherscan.io/api?module=contract&action=getabi&address=0x8ad599c3a0ff1de082011efddc58f1908eb6e6d8&format=raw) |

Each pool has its own address defined by the token pair and the fee. Finding the address of the pool will involve providing the contract address of the pair along with the fee. The `getPool` function in the UniswapV3Factory contract provides this interface.

## Getting positions data

