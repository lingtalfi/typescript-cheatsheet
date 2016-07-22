Typescript Cheatsheet
=========================
2016-07-22



```js
var VARIABLE_NAME : type = value
```

## Types
- boolean
- number
- string

## Arrays
```typescript
var list:number[] = [1,2,3];
var list:Array<number> = [1,2,3];
```


## Enum

```typescript
enum Color {Red, Green, Blue};
var c: Color = Color.Green;
```


## Oop

### Properties visibility
```typescript
class Greeter {
	private greeting: string;
	constructor(message: string){
		this.greeting = message;
	}
	public greet() : string{
		return "Hello, " + this.greeting;
	}
}
var greeter:Greeter = new Greeter("world");

```

### Inheritance

```typescript
class Animal {
	name:string;
	contructor(theName:string){ this.name = theName; }
	move(meters: number=0){
		alert(this.name + " moved " + meters + "m.");
	}
}

class Snake extends Animal {
	name:string;
	contructor(name:string){  super(name); }
	move(meters=5){
		alert("Slithering...");
		super.move(meters);
	}
}
```


### Accessors

```typescript
class Person {
	private _password: string;

	get password(): string {
		return this._password;
	}

	set password(p: string){
		if(p != "123456"){
			this._password = p;
		}
		else{
			alert("Hey, the password can not be: 123456");
		}
	}
}

var p = new Person();
p.password = "123456"; // shows the error
```

### Static, interfaces

```typescript
class SystemAlert{
	static alert(message:string):void{
		alert(message);
	}
}

interface Point {
	x: number;
	y: number;
}

class Point3d implements Point{
	// ...
}

```

### Optional parameter, rest parameters, json params

```typescript
class Foo {
	buildName(firstName: string, lastName?: string){
		if(lastName){
			// ...	
		}
	}	
}

class Foo2 {
	static alertName(firstName: string, ...restOfName: string[]) {
		alert(firstName + " " + restOfName.join(" "));
	}
}

class Foo3 {
	constructor( p: {x:number; y:number; z?:number;} ){

	}
}

```



### Decorators


```typescript
import {Component} from 'angular2/core';

@Component({
	selector: 'my-app',
	template: '<h1>My First Angular 2 App</h1>',
})
export class AppComponent{ }
```


