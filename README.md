# Greek Utilities
-----

A JavaScript library for Greek language with utilities such as replacement of accented and other diacritics characters, conversion from greek to latin (a.k.a. greeklish) and more.

[![NPM](https://nodei.co/npm/greek-utils.png)](https://nodei.co/npm/greek-utils/)

Installation
----------
```javascript
npm install --save greek-utils
````

Usage
-----

### Node.js
```javascript
var greekUtils = require('greek-utils');
```

### - sanitizeDiacritics()
Convert all diacritics symbols to their simple equivalent

Example 1 (modern Greek):
```javascript
var sanitized = greekUtils('Αρνάκι άσπρο και παχύ').sanitizeDiacritics();
console.log(sanitized.text); //Αρνακι ασπρο και παχυ
```
Example 2 (ancient Greek):
```javascript
var sanitized = greekUtils('Ἐξ οὗ καὶ δῆλον ὅτι οὐδεμία τῶν ἠθικῶν ἀρετῶν φύσει ἡμῖν ἐγγίνεται').sanitizeDiacritics();
console.log(sanitized.text); //Εξ ου και δηλον οτι ουδεμια των ηθικων αρετων φυσει ημιν εγγινεται
```

### - toGreek()
Convert a latin characters (a.k.a. greeklish) text to Greek equivalent

Example:
```javascript
var greek = greekUtils('kalhmera, pws eiste?').toGreek();
console.log(greek.text); //καλημερα, πως ειστε?
```

### - toGreeklish()
Convert a Greek characters text to greeklish equivalent

Example:
```javascript
var greeklish = greekUtils('Το κάλλος είναι η καλύτερη συστατική επιστολή').toGreeklish();
console.log(greeklish.text); //To kallos einai h kalyterh systatikh epistolh.
```

### - Chaining method
Run multiple greekUtils functions within a single statement

Example
```javascript
var greek = greekUtils('Αχ, αφτάκια μου και μακριά μουστάκια μου, η ώρα πέρασε!').sanitizeDiacritics().toGreeklish();
console.log(greek.text); //Ax, aftakia mou kai makria moustakia mou, h wra perase!
```
