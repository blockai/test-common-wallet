## test common wallet

A test Common Wallet object for testing software written to the commonWallet spec.

## Inputs

Note common wallet relies on a common blockchain client which can be found <a href="">here</a>
A common wallet instance can be instantiated as follows:

```javascript
var cw = require('test-common-wallet')({
  network: (network you want to operate on. "testnet" or "mainnet"),
  wif: (your private key in wif format to sign messages and transactions),
  address: (your wallet address),
  commonBlockchain: (a Common Blockchain client. Read about this in the link above)
});
```


## Functions

```javascript
//callback should be of the form (err, response)
cw.signMessage("hey there, this is a message", callback);

//this callback should be of the form (err, signedTxHex, txid)
cw.signTransaction((some unsigned transaction hex to sign), callback);

//will create, sign, and (optionally) propagate a transaction. callback should be of (err, response)
cw.createTransaction({
  valueInBTC: (the amount of btc to be transacted),
  destinationAddress: (the address your Common Wallet object will be sending btc to)
}, callback);
```

## Other Common Wallet Data

In addition to the three functions listed above, a common wallet object will also have these two fields:

```
  address: (the public address of the wallet)
  network: (the network the wallet is operating on)
```