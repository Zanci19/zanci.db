# Zanci.DB
- Simple json database. Backup system included!

## How to start?
- Install the project first by using:
```
npm i zanci.db
```
- Don't forget to define it!
```javascript
const { Database } = require('zanci.db')
const db = new Database("MySuperSecretDatabase.json")
```
- Typescript support added as well!
```ts
import { Database } from 'zanci.db';
const db = new Database();
```

## Good to know
- Now if a file doesn't exist, it will automatically create it!
- Path is automatically set to "**./**"

## Examples
- Define an object and push it to the file.
```javascript
let object1 = {key: true, key2: "true"}
db.set('Object', object1); // Object: {key: "value1", key2: "value2"}
```
- Define an array and push it to the file.
```javascript
let array1 = ['element', 'element2']
db.set('Array', array1); // Array: ['element', 'element2']
db.push('Array', 'element3'); // Array: ['element', 'element2', 'element3']
```
- Fetch an object / array.
```javascript
db.objectFetch('Object', 'key'); // key: "value1"
db.arrayFetch('Array', 1); // element2
```
- Fetch data in the file.
```javascript
db.fetch('data'); // Fetches the value of the data
db.get('data'); // Get the value of the data
db.fetchAll(); // Fetches all the data in the database
db.all(); // Fetches everything in the database
```
- Remove data in the file.
```javascript
db.remove('data'); // Removes the data from the database
db.delete('Array', 'element3'); // Removing something from an array using value
db.deleteKey('object', 'key'); // Deletes the provided key from the given object
db.deleteEach('data'); // Deletes each data that starts with the given parameter
```
- Remove database content. Carefully with this!
```javascript
db.clear(); // Clears everything from the database
db.destroy(); // Deletes the database file
```
- Boolean functions.
```javascript
db.has('data'); // Returns "true" or "false" if the database has the data or not.
```
- Math functions.
```javascript
db.add('data', 1); // Adds one to the data
db.subtract('data', 1); // Subtracts one from the data
db.math("eco", "+", 10); // Adds 10 to the data. You can use +, -, * and /.
```