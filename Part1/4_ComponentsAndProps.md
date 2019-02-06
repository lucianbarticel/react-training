# Components and props

> __A component is one isolated piece of interface.__
![components](https://jaxenter.com/wp-content/uploads/2018/07/react-intro-1.png)


> __A component is a reusable chunk of code.__

#### Function and Class Components

```
# function component
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
```
is equivalent to: 

```
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```
but without some certain features.

#### Composing

```
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

function App() {
  return (
    <div>
      <Welcome name="Sara" />
      <Welcome name="Cahal" />
      <Welcome name="Edite" />
    </div>
  );
}
```

#### Extracting

[demo](https://codepen.io/pen?editors=0010)

#### Props

__All React components must act like pure functions with respect to their props.__

---
[resource 1](https://dev.to/sarah_chima/an-introduction-to-react-components-cke)

[resource 2](https://reactjs.org/docs/components-and-props.html)
