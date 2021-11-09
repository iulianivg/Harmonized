# Instructions for Audit

This repository contains the code we use for creating a staking yield aggregator. 
The business core operations is us allowing users to participate in staking in a decentralized way, 
and having their profits reinvested while they are managed by us (also in a dencetralized way)

## Information for smart contracts

We have two smart contracts operated by us: HarmonyVaultV6 and Strategy


### HarmonyVaultV6

This is the vault in which users deposit funds by calling "deposit" function. On each deposit we mint tokens to the user which they can use to withdraw their funds anytime they wish.
The vault is directly connected to our strategy smart contract below. 

### Strategy Smart Contract
This is the main smart contract that we will use to manage funds. We will use automatic scripts in order to 
call "managerHarvest" function every 24 hours and auto-reinvest users' earnings. We take a small fee from users' earnings which can be read in "chargeFees" internal function