# Rendering and Virtual DOM

__Elements__ = the smallest building block in react

```
#root DOM. everything inside is managed by ReactDOM.
<div id="root"></div>
```
Applications usually have 1 root DOM node.

```
const element = <h1>Hello, world</h1>;
ReactDOM.render(element, document.getElementById('root'));
```
__Elements__ = immutable

React DOM compares the updated children and only __updates what's necessary__

![updates](https://reactjs.org/granular-dom-updates-c158617ed7cc0eac8f58330e49e48224.gif)

__Virtual DOM__ = 'virtual' representation of an UI kept in memory and synced with the 'real' DOM by ReactDOM in a process called __reconciliation__. A concept implemented by libraries in JavaScript on top of browser APIs.



since React 16, __React Fiber__ is the new reconciliation engine.

__Virtual DOM != Shadow DOM__ ( A browser technology designed primarily for scoping variables and CSS in web components )
