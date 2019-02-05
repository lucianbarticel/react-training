# JSX
---

> __The major benefit of using JSX is that you’re only interacting with JavaScript object, not template strings.__

#### Why JSX?

NO: separating technologies (markup & logic)
YES: separating concerns (components)

__!__ React doesn’t require using JSX


#### Embedding Expressions in JSX

```
const name = 'Johny Boy';
const element = <h1>Hello, {name}</h1>;

ReactDOM.render(
  element,
  document.getElementById('root')
);
```

__!__ You can put any valid [JavaScript expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#Expressions) inside the curly braces in JSX

#### JSX is an Expression Too

JSX expressions become regular JavaScript function calls and evaluate to JavaScript objects. =>

```
function getGreeting(user) {
  if (user) {
    return <h1>Hello, {formatName(user)}!</h1>;
  }
  return <h1>Hello, Stranger.</h1>;
}
```

#### Specifying The React Element Type

The first part of a JSX tag determines the type of the React element.

__!__ letter case = build in components (`<div>`, `<span>`);

__!__ `<Foo />` must be capitalized and in scope.

__!__ `React` must be in scope too.


```
/*  the React library. It contains methods that you need in order to use React. */
import React from "react"; 

/* a JavaScript library which contains several methods that deal with the DOM in some way. */
import ReactDOM from "react-dom";
```

__!__ `<Foo.Bar />` <- dot notation also available

__!__ `<components[props.storyType] />` <- general expression is not

fix: 
```
const FooBar = components[props.storyType];
<FooBar />
```

#### Specifying Attributes with JSX

```
const element = <div tabIndex="0"></div>;
```
or
```
const element = <img src={user.avatarUrl}></img>;
```
__!__ not:
```
const element = <img src="{user.avatarUrl}"></img>;
```

__in jsx:__
- attributes that have dashes (-) are converted to camelCase
- `class` becomes `className`

#### Specifying Children with JSX

If tag has no children, you can close it immediately with `/>`.

#### JSX Prevents Injection Attacks

By default, React DOM escapes any values embedded in JSX before rendering them. 

Everything is converted to a string before being rendered.

This helps prevent [XSS (cross-site-scripting)](https://en.wikipedia.org/wiki/Cross-site_scripting) attacks.

#### JSX Represents Objects

__!__ Babel compiles JSX down to React.createElement() calls.


```
const element = (
  <h1 className="greeting">
    Hello, world!
  </h1>
);
```
compiles into:
```
const element = React.createElement(
  'h1',
  {className: 'greeting'},
  'Hello, world!'
);
```
`React.createElement` creates a structure (React element) like:

```
// Note: this structure is simplified
const element = {
  type: 'h1',
  props: {
    className: 'greeting',
    children: 'Hello, world!'
  }
};
```

__React reads these objects and uses them to construct the DOM and keep it up to date.__


[jsx translated to js](https://babeljs.io/repl/#?presets=react&code_lz=DwEwlgbgBAxgNgQwM5IHIILYFMC8AiJACwHsAHUsAOwHMBaOMJAFzwD4AoKKYQgRlYDKJclWpQAMoyZQAZsQBOUAN6l5ZJADpKmLAF9gAej4cuwAK5wTXbg1YBJSswTV5mQ7c7XgtgOqEETEgAguTuYFamtgDyMBZmSGFWhhYchuAQrADc7EA)




---
[resource 1](https://reactjs.org/docs/introducing-jsx.html)
[resource 2](https://reactjs.org/docs/jsx-in-depth.html)
[resource 3](https://jaxenter.com/introduction-react-147054.html)
