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
