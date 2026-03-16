
```js
'use strict';

const obj = {
	a: 5,
	b: 1
};

const copy = obj //Ссылка

copy.a = 10;

console.log(copy);
console.log(obj);
```
При попытке присваивание объектов, массивов, функций, кладется ссылка на уже существующий объект. Все изменения производящие с этим объектом, так же будет влиять на тот же самый объект.

## Создание копии объектов... через цикл

```js
'use strict';

function copy(mainObj) {
	let objCopy = {};
	
	let key;
	for (key in mainObj) {
		objCopy[key] = mainObj[key];
	}
	
	return objCopy;
}

const numbers = {
	a: 2,
	b: 5,
	c: {
		x: 7,
		y: 4
	}
};

const newNumbers = copy(numbers);

console.log(newNumbers);
console.log(numbers);
```


<mark class="hltr-b">Поверхностная копия объетов</mark> - это происходит копирование на уровне родителей
```js
'use strict';

function copy(mainObj) {
	let objCopy = {};
	
	let key;
	for (key in mainObj) {
		objCopy[key] = mainObj[key];
	}
	
	return objCopy;
}

const numbers = {
	a: 2,
	b: 5,
	c: {
		x: 7,
		y: 4
	}
};

const newNumbers = copy(numbers);

newNumbers.c.x = 10; // Срабатывает ссылка на уже существующий объект, так как 

console.log(newNumbers);
console.log(numbers);
```

## Создание копии объектов через Object.assign

```js
'use strict';

function copy(mainObj) {
	let objCopy = {};
	
	let key;
	for (key in mainObj) {
		objCopy[key] = mainObj[key];
	}
	
	return objCopy;
}

const numbers = {
	a: 2,
	b: 5,
	c: {
		x: 7,
		y: 4
	}
};

const newNumbers = copy(numbers);

newNumbers.c.x = 10; // Срабатывает ссылка на уже существующий объект, так как 

console.log(newNumbers);
console.log(numbers);

const add = {
	d: 17,
	e: 20
};

//console.log(Object.assign(Объект в который хотим поместить, объект который помещаем))
console.log(Object.assign(numbers, add));

```

Создание нового объекта

```js
'use strict';

function copy(mainObj) {
	let objCopy = {};
	
	let key;
	for (key in mainObj) {
		objCopy[key] = mainObj[key];
	}
	
	return objCopy;
}

const numbers = {
	a: 2,
	b: 5,
	c: {
		x: 7,
		y: 4
	}
};

const newNumbers = copy(numbers);
const add = {
	d: 17,
	e: 20
};

const clone = Object.assign({}, add);

clone.d = 20;
console.log(add);
console.log(clone);

```
