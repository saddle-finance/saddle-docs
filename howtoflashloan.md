# How to Flash-loan Assets from Saddle Pools

Some of our pools allow flash-loaning assets for a small fee.

```solidity
function flashLoan(
    address receiver,
    IERC20 token,
    uint256 amount,
    bytes memory params
) external;
```

Caller must provide a valid receiver address that inherits [IFlashLoanReceiver interface](https://github.com/saddle-finance/saddle-contract/blob/master/contracts/interfaces/IFlashLoanReceiver.sol).

```solidity
function executeOperation(
    address pool,
    address token,
    uint256 amount,
    uint256 fee,
    bytes calldata params
) external;
```

Upon finishing `executeOperation`, the pool must have the initial liquidity back along with the associated fee. If the requirement is not met, then the transaction will fail.

We provide a [basic example of a flashloan borrower contract](https://github.com/saddle-finance/saddle-contract/blob/master/contracts/helper/FlashLoanBorrowerExample.sol).

### Flash-loan Supported Pools

- vETH2 pool (`0xdec2157831D6ABC3Ec328291119cc91B337272b5`)
- alETH pool (`0xa6018520EAACC06C30fF2e1B3ee2c7c22e64196a`)
- D4 pool (`0xC69DDcd4DFeF25D8a793241834d4cc4b3668EAD6`)
