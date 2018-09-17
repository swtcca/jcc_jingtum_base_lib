# The Jingtum Base JavaScript Library

[![Build Status](https://travis-ci.com/JCCDex/jcc_jingtum_base_lib.svg?branch=master)](https://travis-ci.com/JCCDex/jcc_jingtum_base_lib)
[![Coverage Status](https://coveralls.io/repos/github/JCCDex/jcc_jingtum_base_lib/badge.svg?branch=master)](https://coveralls.io/github/JCCDex/jcc_jingtum_base_lib?branch=master)

<!-- Basic function for development, include generate wallet, check secret and check address.

`jcc_jingtum-base-lib` connects to the Jingtum base lib and runs in Node.js as well as in the browser.

## Getting `jcc_jingtum-base-lib`

**Via npm for Node.js**

```
  $ npm install jcc_jingtum-base-lib
```

**Build from the source using `gulp`**

```
  $ git clone https://github.com/JCCDex/jcc_jingtum-base-lib.git
  $ npm install
  $ gulp
```

Then use the minified `dist/jcc_jingtum-base-*-min.js` in your webpage

## Quickstart
```
    var Wallet = require('jcc_jingtum-base-lib').Wallet;
    var wallet1 = Wallet.generate('SWT');//create a wallet by currency
    var wallet2 = Wallet.fromSecret('saai2npGJD7GKh9xLxARfZXkkc8Bf','SWT');//get a wallet by secret
    var ret = Wallet.isValidAddress('j98a2BFmVQDSCvQEQEAF9tE8JWpvLqRuUM','SWT');// whether the address is valid
    var ret = Wallet.isValidSecret('saai2npGJD7GKh9xLxARfZXk kc8Bf','SWT');// whether the secret is valid
```
## Signature verification
```
  var wt = new Wallet('saai2npGJD7GKh9xLxARfZXkkc8Bf','SWT');
  var pubkey = wt.getPublicKey();

  // Sign message can be an array or a hex string
  var sdata = "F95EFF5A4127E68D2D86F9847D9B6DE5C679EE7D9F3241EC8EC67F99C4CDA923";

  var sign =wt.sign(sdata);

  // Signature MUST be either:
  // 1) hex-string of DER-encoded signature; or
  // 2) DER-encoded signature as buffer; or
  // 3) object with two hex-string properties (r and s)
  // Verify the signature 
  if ( wt.verify(sdata, sign) == true)
  {
    console.log("Verify sjcl signature successfully!");
  }else
    console.log("Cannot verify sjcl sig");

```
## TODO
   Check if work in browser env -->