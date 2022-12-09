# UptickProposal
As described by the Uptick Team in a Medium article (https://uptickproject.medium.com/game-of-uptick-testnet-optimized-submission-process-5f63ae5595ce) the contributions have to be voted on through governance. This small post is to provide the group of validators a template and the set of commands to upload the proposal on chain. Note that this guide is for the proposal type as known in Cosmos SDKv0.45.x and earlier. Since Uptick is on SDKv0.46.x a newer format is also present, but that has not been described fully yet.

## Prepare the proposal file
The easiest route is to prepare the proposal file before you are sending the tx on chain. 

Create a new file:
```
nano $HOME/.uptickd/[filename].json
```

Add in this file the proposal text. Most will be text proposals, so this guide is written for a text proposal:
```
{
  "title": "[Proposal title]"
  "description": "[Proposal description]"
  "type": "Text"
  "deposit": 10000000000000000000auptick"
}
```
Save and exit the file ("Ctrl + X", followed by "Y")

The file is now prepared, time for the following step.

## Sending the tx
Make sure to have enough funds and send the following tx on chain:
```
uptickd tx gov submit-legacy-proposal --proposal="$HOME/.uptickd/[filename].json --from [your_wallet_name] --gas auto --gas-adjustment 1.5 --gas-prices 0.025auptick --chain-id uptick_7000-2 -y
```

Good luck!!

## Proposal types
Other possible types are:
- cancel-software-upgrade
- community-pool-spend
- ibc-upgrade
- param-change
- register-coin
- register-erc20
- register-erc721
- register-nft
- software-upgrade
- toggle-token-conversion
- toggle-token-relay
- update-client
Note that a different proposal type might also require more content in the [filename].json
