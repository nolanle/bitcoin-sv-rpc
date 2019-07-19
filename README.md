# Bitcoin SV JSON-RPC library

## Javascript Library to communicate with your Bitcoin Unlimited / Bitcoin SV / Bitcoin Classic Node.

![header](https://bitcoinsv.io/wp-content/uploads/2019/01/BSV_nav_bar_logo.png)

This is a promise-based library and `async/await` compatible. Includes a couple
additional helpers, such as a QRcode generator as well as Bitpay's Address
translator. Supports both address formats.

## Installation

grab from NPM

```
  npm i bitcoin-sv-rpc
```

## Usage

```
let bsvRPC = require("bitcoin-sv-rpc");
let bsv = new bsvRPC(host, username, password, port, timeout, debugging);

// timeout is 3000 by default
// debugging is true by default, false makes the library silent and requires try/catch on the app level.


```

```
 let info = await bsv.getInfo();

 console.log(info)

 // results in
 //{
 //  "version": 1010101,
 //  "protocolversion": 80003,
 //  "walletversion": 60000,
 //  "balance": 0.00000000,
 //  "blocks": 478559,
 //  "timeoffset": 0,
 //  "connections": 12,
 //  "proxy": "",
 //  "difficulty": 29829733124.04042,
 //  "testnet": false,
 //  "keypoololdest": 1506057198,
 //  "keypoolsize": 100,
 //  "paytxfee": 0.00000000,
 //  "relayfee": 0.00001000,
 //  "errors": "",
 //  "fork": "Bitcoin SV"
 //}

```

or

```
 p = Promise.resolve(bsv.getInfo());
 p.then(info=>{
    console.log(info);
 })
```

## Available Methods

there is incomplete coverage at the moment. Please submit a PR if you'd like to
have a method added.

`getInfo` `getBlockCount` `getWalletInfo` `getUnconfirmedBalance` `getBalance`
`getWalletInfo` `getBlockHash` `getNewAddress` `setTxFee` `validateAddress`
`sendToAddress` `sendFrom` `getAccountAddress` `getBlock` `getTxOut`
`listTransactions` `listUnspent` `estimateSmartFee` `getTransaction`
`getRawTransaction` `getRawMempool` `getRawChangeAddress` `signRawTransaction`
`sendRawTransaction` `decodeRawTransaction` `getTxoutProof`

## Compatible Node Implementations

You must be running a Node (Pruned mode is fine)

[Bitcoin SV](https://bitcoinsv.io/)

[Bitcoin XT ](https://bitcoinxt.software/)

[Bitcoin Unlimited (Cash)](https://www.bitcoinunlimited.info/)

### Tested on Node v7.10, and npm v5.4.1
