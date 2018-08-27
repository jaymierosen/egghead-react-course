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

<h2>1. Create HTML elements with React's createElement API</h2>
  <p>This is how you can render content to the DOM without using React:</p>
  <pre class="language-bash">
    <code class="language-bash">
      const rootElement = document.getElementById('root');
      const element = document.createElement('div');
      element.textContent = 'Hello, world!';
      element.className = 'container';
      rootElement.appendChild(element);
    </code>
  </pre>
  <p>This is how to render content to the DOM using React:</p>
  <pre class="language-bash">
    <code class="language-bash">
      const rootElement = document.getElementById('root');
      const element = React.createElement(
        'div',
        { className: 'container',
        children: ['Hello, world!'] },
      );
      ReactDOM.render(element, rootElement);
    </code>
  </pre>
  <p>To create an <code>element</code>, you write <code>React.createElement</code> and you pass it an HTML element, and an object containing <code>props</code>.</p>
  <p><code>console.log(element)</code> will expose the <code>element</code> object. You will find under <code>props</code> both <code>children</code> and <code>className</code>. The <code>children</code> represents the text content and the <code>className</code> is the <code>class</code> associated to the <code>element</code>.</p>
  <p><code>ReactDOM.render(element, rootElement);</code> renders out the <code>root</code> and the <code>element</code> variables.</p>
  <h2>2. Replace React createElement Function Call with JSX</h2>
  <p>An easier way to render an element is by using <strong>JSX</strong>:</p>
  <pre class="language-bash">
    <code class="language-bash">
      const element = < div className="container">Hello, world < /div >;
    </code>
  </pre>
  <p><strong>Interolation</strong>: we provide a variable with content as the value, and use { } to render out the value in the container div:</p>
  <pre class="language-bash">
    <code class="language-bash">
      const content = 'Hello, world';
      const element = < div className="container">{content}< /div >;
    </code>
  </pre>
  <p>You can also use interpolation on the <code>className</code>, too:</p>
  <pre class="language-bash">
    <code class="language-bash">
      const content = 'Hello, world';
      const className = 'container';
      const element = < div className={className + '__hi-there'}>{content}< /div>;
    </code>
  </pre>
  <p>Alternatively, you can create a <code>props</code> object:</p>
  <pre class="language-bash">
    <code class="language-bash">
      const content = 'Hello, world';
      const className = 'container';
      const props = {
        children: 'Hello, world!',
        className: 'container'
      }
      const element = < div className={props.className + '__hi-there'}>{props.content}< /div>;
    </code>
  </pre>
  <p>By using the <code>spread operator</code>, you can do cool stuff like:</p>
  <pre class="language-bash">
    <code class="language-bash">
      const element = < div {...props} />
    </code>
  </pre>
  <h2>3. Create a Simple Reusable React Component</h2>
  <p>Interolation:</p>
  <pre class="language-bash">
    <code class="language-bash">
      const HelloWorld = < div>Hello, world!< /div>
      const element = < div className="container">{HelloWorld}< /div>
    </code>
  </pre>
  <p>When we want to pass in <code>props</code> to render different two different pieces of content:</p>
  <pre class="language-bash">
    <code class="language-bash">
      const Message = (props) => <div>{props.msg}</div>
      const element =
        <div className="container">
          <Message msg='Hello, world!' />
          <Message msg='Goodbye, world!' />
          // {React.createElement(Message, {msg: 'Hello, world!'})}
          // {React.createElement(Message, {msg: 'Goodbye, world!'})}
        </div>
    </code>
  </pre>
