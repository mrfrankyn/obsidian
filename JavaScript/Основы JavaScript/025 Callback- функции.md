```js
'use strict';

function learnJS(lang, callback) {
	console.log(`Я учу: ${lang}`);
	callback();	
}

learnJS('JavaScript', function() {
	console.log('Я прошел этот урок!');
})
```

```js
'use strict';

function learnJS(lang, callback) {
	console.log(`Я учу: ${lang}`);
	callback();	
}

function done() {
	console.log('Я прошел этот урок!');
}

learnJS('JavaScript', done);
```
