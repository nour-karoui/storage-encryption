Encrypt your client storage (available for TS & JS)

<h1 align="center">Welcome to Encrypt Storage 👋</h1>
<p>
  <a href="https://www.npmjs.com/package/storage-encryption" target="_blank">
    <img alt="Version" src="https://img.shields.io/npm/v/storage-encryption.svg">
  </a>
  <a href="https://github.com/nour-karoui/storage-encryption#readme" target="_blank">
    <img alt="Documentation" src="https://img.shields.io/badge/documentation-yes-brightgreen.svg" />
  </a>
  <a href="https://github.com/nour-karoui/storage-encryption/graphs/commit-activity" target="_blank">
    <img alt="Maintenance" src="https://img.shields.io/badge/Maintained%3F-yes-green.svg" />
  </a>
  <a href="https://github.com/nour-karoui/storage-encryption/blob/master/LICENSE" target="_blank">
    <img alt="License: MIT" src="https://img.shields.io/github/license/bishkou/password-pwnd" />
  </a>
</p>

* **Encrypt your storage using AES symmetric encryption algorithm**

* **JS and TS**


### 🏠 [Homepage](https://github.com/nour-karoui/storage-encryption)

## Install

```sh
npm i @storage-encryption/storage-encryption
```

## How it works

* **The constructor of EncryptedStorage takes two arguments:**
    * **secret**(required): the secret key (a string) that we'll use in the encryption
    * **storage**(optional): localStorage / sessionStorage.
     storage is localStorage by default.
     
* **Methods provided by encryptedStorage:**
    * **encrypt**(storage_key: string, data: any): void
    * **decrypt**(storage_key: string): any
    * **remove**(storage_key: string): void
    

## Encrypt Local/Session Storage (For Typescript)

```ts
import {EncryptStorage} from '@storage-encryption/storage-encryption';

// the constructor takes the secret key as a first parameter and an optional
// second parameter as the storage type
// if none is provided it'll be localStorage by default
const encryptStorage = new EncryptStorage(SECRET_KEY, 'sessionStorage');
/*** for a string ***/
encryptStorage.encrypt('storage_key', 'Hello world');
const stringValue = encryptStorage.decrypt('storage_key');

/*** for an object ***/
encryptStorage.encrypt('storage_key', {'name': 'Hello world'});
const objectValue = encryptStorage.decrypt('storage_key');

/*** for a number ***/
encryptStorage.encrypt('storage_key', 1);
const numberValue = encryptStorage.decrypt('storage_key');

/*** for an array ***/
encryptStorage.encrypt('storage_key', [1, 2, 3]);
const arrayValue = encryptStorage.decrypt('storage_key');

encryptStorage.remove('storage_key'); 
```

## Encrypt Local/Session Storage (For Javascript)
```js
const { EncryptStorage } = require('@storage-encryption/storage-encryption')

const encryptStorage = new EncryptStorage(SECRET_KEY, 'localStorage');
/*** for a string ***/
encryptStorage.encrypt('storage_key', 'Hello world');
const stringValue = encryptStorage.decrypt('storage_key');

/*** for an object ***/
encryptStorage.encrypt('storage_key', {'name': 'Hello world'});
const objectValue = encryptStorage.decrypt('storage_key');

/*** for a number ***/
encryptStorage.encrypt('storage_key', 1);
const numberValue = encryptStorage.decrypt('storage_key');

/*** for an array ***/
encryptStorage.encrypt('storage_key', [1, 2, 3]);
const arrayValue = encryptStorage.decrypt('storage_key');

encryptStorage.remove('storage_key'); 
```

## A BETTER WAY TO DO IT
* **Instantiate the encryptStorage object in a shared folder and export it**
* **So you won't have to instantiate it in each file**

````ts
import EncryptStorage from '@storage-encryption/storage-encryption';

export const encryptSessionStorage = EncryptStorage(SECRET_KEY, 'sessionStorage');
export const encryptLocalStorage = EncryptStorage(SECRET_KEY);

````
## Author

👤 **Nour**

* Github: [@nour-karoui](https://github.com/nour-karoui)
* LinkedIn: [@nourkaroui](https://www.linkedin.com/in/nourkaroui/)

## 🤝 Contributing

Contributions, issues and feature requests are welcome!<br />Feel free to check [issues page](https://github.com/nour-karoui/encrypt-storage/issues). You can also take a look at the [contributing guide](https://github.com/nour-karoui/encrypt-storage/blob/master/CONTRIBUTING.md).

## Show your support

Give a [STAR](https://github.com/nour-karoui/storage-encryption) if this project helped you!

## 📝 License

* Copyright © 2021 [Nour](https://github.com/nour-karoui).
* This project is [MIT](https://github.com/nour-karoui/storage-encryption/blob/master/LICENSE) licensed.

***
_This README was generated with by [readme-md-generator](https://github.com/kefranabg/readme-md-generator)_
