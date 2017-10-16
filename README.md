# SimpleCryptoJS 1.0.0

SimpleCryptoJS is a JavaScript library that simplify the process of encryption and decryption of JavaScript objects, as simple as just calling `encrypt()` and `decrypt()` function. This library implementing brix's [crypto-js](https://github.com/brix/crypto-js) library. This library is pure JavaScript library built with TypeScript targeting ECMAScript 5 (ES5), so it is compatible with most NodeJS back-end applications or JavaScript front-end (client browser).

## Getting Started

This library package distribution is availabe through `npm` and (soon) through CDN.

### Installing

To get this library included on your project/application, just hit `npm install` command and then import SimpleCryptoJS to your project/application.

```
npm install --save simple-crypto-js
```

If you are using the new ECMAScript 6 (ECMAScript 2015) and later, you may use the new import statement:

```
// ECMAScript 6 and later
import SimpleCryptoJS from 'simple-crypto-js';
```

However, if you are using ECMAScript 5 and older, use the require statement:

```
// ECMAScript 5 and older
var SimpleCryptoJS = require('simple-crypto-js').SimpleCryptoJS;
```

## Documentation

SimpleCryptoJS 1.0.0 has a single class with only 5 function to keep it's simplicity. This is full documentation about the library and how to use it on your project/application, all with examples on both ECMAScript 6 (and later) and ECMAScript 5 (and older).

### Using SimpleCryptoJS Object Instance's `encrypt()` and `decrypt()`

To use SimpleCryptoJS, first create a SimpleCryptoJS object and instatiate with a secret key (password). Secret key parameter MUST be defined when creating a SimleCryptoJS object.

To encrypt and decrypt string objects, just use `encrypt()` and `decrypt()` function. This will use AES-CBC encryption algorithm.

```
// ECMAScript 6 and later 
const SECRET_KEY = 'some-unique-key';
/**
 * // if you would like to generate a random unique key, you may use static function generateRandom() like so
 * const SECRET_KEY = SimpleCryptoJS.generateRandom();
 * // you may also set the strength of the random key, as example 256 (default is 128);
 * const SECRET_KEY = SimpleCryptoJS.generateRandom(256);
 */
let simpleCrypto = new SimpleCryptoJS(SECRET_KEY);

let plainText = 'Hello World!';
let chiperText = simpleCrypto.encrypt(plainText);
console.log(`Encryption process...`);
console.log(`Plain Text    : ${plainText}`);
console.log(`Cipher Text   : ${cipherText}`);
let decipherText = simpleCrypto.decrypt(cipherText);
console.log(`... and then decryption...`);
console.log(`Decipher Text : ${cipherText}`);
console.log(`... done.`);
```

```
// ECMAScript 5 and older
var secretKey = 'some-unique-key';
/**
 * // if you would like to generate a random unique key, you may use static function generateRandom() like so
 * var secretKey = SimpleCryptoJS.generateRandom();
 * // you may also set the strength of the random key, as example 256 (default is 128);
 * var secretKey = SimpleCryptoJS.generateRandom(256);
 */
var simpleCrypto = new SimpleCryptoJS(SECRET_KEY);

var plainText = 'Hello World!';
var chiperText = simpleCrypto.encrypt(plainText);
console.log("Encryption process...");
console.log("Plain Text    : " + plainText);
console.log("Cipher Text   : " + cipherText);
var decipherText = simpleCrypto.decrypt(cipherText);
console.log("... and then decryption...");
console.log("Decipher Text : " + cipherText);
console.log("... done.");
```

### Working on Multiple SimpleCryptoJS Object Instances

You also could perform the encryption and decryption process using different SimpleCryptoJS object instances, AS LONG AS the secret keys ARE STAY THE SAME between the object instances. For example:

```
// ECMAScript 6 and later 
const SECRET_KEY = 'some-unique-key';
let simpleCrypto1 = new SimpleCryptoJS(SECRET_KEY);
let simpleCrypto2 = new SimpleCryptoJS(SECRET_KEY);

let plainText = 'Hello World!';
let chiperText = simpleCrypto1.encrypt(plainText);
console.log(`Encryption process...`);
console.log(`Plain Text    : ${plainText}`);
console.log(`Cipher Text   : ${cipherText}`);
let decipherText = simpleCrypto2.decrypt(cipherText);
console.log(`... and then decryption...`);
console.log(`Decipher Text : ${cipherText}`);
console.log(`... done.`);
```

```
// ECMAScript 5 and older 
var secretKey = 'some-unique-key';
var simpleCrypto1 = new SimpleCryptoJS(SECRET_KEY);
var simpleCrypto2 = new SimpleCryptoJS(SECRET_KEY);

var plainText = 'Hello World!';
var chiperText = simpleCrypto1.encrypt(plainText);
console.log("Encryption process...");
console.log("Plain Text    : " + plainText);
console.log("Cipher Text   : " + cipherText);
var decipherText = simpleCrypto2.decrypt(cipherText);
console.log("... and then decryption...");
console.log("Decipher Text : " + cipherText);
console.log("... done.");
```

### SimpleCryptoJS Secret Property

If you want to change the secret key of a SimpleCryptoJS object, just use `secret` property of the object.

```
// ECMAScript 6 and later 
let simpleCrypto = new SimpleCryptoJS('some-unique-key';);

console.log(`Current Secret Key : ${simpleCrypto.secret}`);
simpleCrypto.secret = 'new-more-unique-key';
console.log(`New Secret Key     : ${simpleCrypto.secret}`);
```

```
// ECMAScript 5 and older 
var simpleCrypto = new SimpleCryptoJS('some-unique-key');

console.log("Current Secret Key : " + simpleCrypto.secret);
simpleCrypto.secret = 'new-more-unique-key';
console.log("New Secret Key     : " + simpleCrypto.secret);
```

### Object Encryption

Encryption and decryption of any JavaScript object has never been simpler than this. As easy as the string one, just use `encryptObject()` and `decryptObject()` function. This will also use AES-CBC encryption algorithm.

```
// ECMAScript 6 and later 
const SECRET_KEY = 'some-unique-key';
/**
 * // if you would like to generate a random unique key, you may use static function generateRandom() like so
 * const SECRET_KEY = SimpleCryptoJS.generateRandom();
 * // you may also set the strength of the random key, as example 256 (default is 128);
 * const SECRET_KEY = SimpleCryptoJS.generateRandom(256);
 */
let simpleCrypto = new SimpleCryptoJS(SECRET_KEY);

let object = {
  data : 'Very sensitive and crucial information.',
  owner: 'The Author'
};
let encrypted = simpleCrypto.encryptObject(plainObject);
console.log(`Encryption process...`);
console.log(`Plain Object     : ${plainObject}`);
console.log(`Encrypted Object : ${encrypted}`);
let decrypted = simpleCrypto.decryptObject(encrypted);
console.log(`... and then decryption...`);
console.log(`Decrypted object : ${decrypted}`);
console.log(`... done.`);
```

```
// ECMAScript 5 and older
var secretKey = 'some-unique-key';
/**
 * // if you would like to generate a random unique key, you may use static function generateRandom() like so
 * var secretKey = SimpleCryptoJS.generateRandom();
 * // you may also set the strength of the random key, as example 256 (default is 128);
 * var secretKey = SimpleCryptoJS.generateRandom(256);
 */
var simpleCrypto = new SimpleCryptoJS(SECRET_KEY);

var object = {
    data: 'Very sensitive and crucial information.',
    owner: 'The Author'
};
var encrypted = simpleCrypto.encryptObject(plainObject);
console.log("Encryption process...");
console.log("Plain Object     : " + plainObject);
console.log("Encrypted Object : " + encrypted);
var decrypted = simpleCrypto.decryptObject(encrypted);
console.log("... and then decryption...");
console.log("Decrypted object : " + decrypted);
console.log("... done.");
```

### Random Key Generator

Anywhere, after importing SimpleCryptoJS, you may use static function `generateRandom(length)` to produce a unique random key based on the length you provided on the parameter (default is 128).

```
// ECMAScript 6 and later
let iNeedSecret = SimpleCryptoJS.generateRandom();
```

```
// ECMAScript 5 and older
var iNeedSecret = SimpleCryptoJS.generateRandom();
```

Yes, of course and obvious, because it is a static function, you are not required to create any SimpleCryptoJS object instances.

## Built With

Written in [TypeScript](http://www.dropwizard.io/1.0.2/docs/), built into ECMAScript 5. 

## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/danang-id/simple-crypto-js/tags). 

## Authors

* **Danang Galuh Tegar Prasetyo** - *Initial work* - [danang-id](https://github.com/danang-id)

See also the list of [contributors](https://github.com/danang-id/simple-crypto-js/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* This library was developed to support and simplify the [Secure Cookies](https://github.com/danang-id/secure-cookies) library.
* Made available by open source and of course brix's [crypto-js](https://github.com/brix/crypto-js) library
