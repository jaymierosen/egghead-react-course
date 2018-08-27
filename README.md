# egghead-react-course
## 1. Create HTML elements with React's createElement API
This is how you can render content to the DOM without using React:
```
const rootElement = document.getElementById('root');
const element = document.createElement('div');
element.textContent = 'Hello, world!';
element.className = 'container';
rootElement.appendChild(element);
```

##1. Create HTML elements with React's createElement API</h2>
This is how you can render content to the DOM without using React:
```
const rootElement = document.getElementById('root');
const element = document.createElement('div');
element.textContent = 'Hello, world!';
element.className = 'container';
rootElement.appendChild(element);
```
This is how to render content to the DOM using React:
```
const rootElement = document.getElementById('root');
const element = React.createElement(
'div',
{ className: 'container',
children: ['Hello, world!'] },
);
ReactDOM.render(element, rootElement);
```
To create an <code>element</code>, you write <code>React.createElement</code> and you pass it an HTML element, and an object containing <code>props</code>.
<code>console.log(element)</code> will expose the <code>element</code> object. You will find under <code>props</code> both <code>children</code> and <code>className</code>. The <code>children</code> represents the text content and the <code>className</code> is the <code>class</code> associated to the <code>element</code>.
<code>ReactDOM.render(element, rootElement);</code> renders out the <code>root</code> and the <code>element</code> variables.
## 2. Replace React createElement Function Call with JSX</h2>
An easier way to render an element is by using <strong>JSX</strong>:
```
const element = <div className="container">Hello, world </div>;
```
Interolation: we provide a variable with content as the value, and use { } to render out the value in the container div:
```
const content = 'Hello, world';
const element = <div className="container">{content}</div>;
```
You can also use interpolation on the <code>className</code>, too:
```
const content = 'Hello, world';
const className = 'container';
const element = <div className={className + '__hi-there'}>{content}</div>;
```
Alternatively, you can create a <code>props</code> object:
```
const content = 'Hello, world';
const className = 'container';
const props = {
children: 'Hello, world!',
className: 'container'
}
const element = <div className={props.className + '__hi-there'}>{props.content}</div>;
```
By using the <code>spread operator</code>, you can do cool stuff like:
```
const element = <div {...props} />
```
## 3. Create a Simple Reusable React Component</h2>
Interolation:
```
const HelloWorld = <div>Hello, world!< /div>
const element = <div className="container">{HelloWorld}</div>
```
When we want to pass in <code>props</code> to render different two different pieces of content:
```
const Message = (props) => <div>{props.msg}</div>
const element =
<div className="container">
<Message msg='Hello, world!' />
<Message msg='Goodbye, world!' />
</div>
```
