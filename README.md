# PunkSwap Contracts

This repository contains all contracts that the PunkSwap DEX uses.

PunkSwap operates on
Scroll https://zkscroll.punkswap.exchange/swap/
Shibarium https://app.punkswap.exchange/
opBNB https://opbnb.punkswap.exchange/

All contracts are open source, verified on the block explorers of the respective chain, secure and battle tested.

We are deliberately a straigth-forward fork of PancakeSwap when it comes to the contracts that our DEX uses. The reason is that we want to use secure, battle tested code for the functions of the DEX. That is why our factory, router and PUNK token contracts are 1:1 copies of the corresponding PancakeSwap contracts just with variable names changed. This makes it easy to compare our contracts to the originals and to see that we did not add any malicious code.

The multicall is only used to read data from the blockchain more efficiently and it is a straight-up 1:1 copy of the template.

For the master chef we used a combination of
https://github.com/slime-fi/slime-contracts/blob/main/SlimeChefWithdrawFee.sol
and
https://github.com/goosedefi/goose-contracts/blob/master/contracts/MasterChefV2.sol
and added a locktime feature.
Both template contracts are popular choices and therefore battle tested.

There are two reasons for us not using the original PancakeSwap masterchef:

1. The original PancakeSwap contract has vulnerabilities that can be exploited. (PancakeSwap used a workaround to prevent further exploitation.)
2. We wanted to have a few more features which are not present in the original PancakeSwap contract but are present in the above mentioned contracts.

We added quite a lot of comments to our masterchef to make it easier to compare our version to the two templates.

Please note that the hash code in the pairFor function of the router contract needs to be adjusted to the blockchain that the contract is deployed to in order to match the output of the factory contract for INIT_CODE_PAIR_HASH.


# Socials

https://t.me/PunkSwapDEX
https://twitter.com/PunkSwapDEX
