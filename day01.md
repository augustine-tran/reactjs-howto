# ReactJS How to

---
# Today topics

- Set-up and Run 1st demo
- ES6 Crash course
- Project structure & Workflow
- Components & JSX Syntax
- And Components ... and components


^ How to ask something about React?

---

# Set-up and Run 1st demo

```bash
npm install -g create-react-app

create-react-app my-app
cd my-app/
npm start
```

Open [Demo](http://localhost:3000/)

---
#  ES6 Crash course
## [fit] An JavaScript file is a module...
```javascript
// file foo.js
const COLOR_THEME = 'Ocean';
function sayHello(name) {
  console.log(`Hello ${name}`);
}
class Foo {
  sum(a, b) {
    return a + b;
  }
}

export default Foo;
export {COLOR_THEME, sayHello};
```

---

#  ES6 Crash course
## [fit] Export and export default
```javascript
export default Foo;
export {COLOR_THEME, sayHello};
```

---
#  ES6 Crash course
## [fit] Import from a module
```javascript
import Foo, {sayHello, COLOR_THEME} from './foo'; //don't need .js for import js

// or only default class Foo
import Foo from './foo';

// or rename to new name
import Foo as Bar from './foo';

// or only sayHello function
import {sayHello}

```

---
#  ES6 Crash course
## [fit] Arrow Function

```javascript
function sum(a, b) {
  return a + b;
}

const sum = (a, b) => a + b;

const arr = [4, 5, 8, 2, 1, 3, 9, 7];
// filter odd number only
console.log(
  arr.filter(number => number % 2 === 0)
);
```
---

# Project Structure & Workflow


---
![right](https://raw.githubusercontent.com/casesandberg/react-color/master/screenshot.png)

# Its dead simple to add new component [React Color](http://casesandberg.github.io/react-color/)


```bash
npm install react-color --save
```

```javascript
import React from 'react';
import { SketchPicker } from 'react-color';

class Component extends React.Component {

  render() {
    return <SketchPicker />;
  }
}
```

---

# index.js
```javascript
import React from 'react';
import ReactDOM from 'react-dom';
import App from './App';

ReactDOM.render(
  <App />,
  document.getElementById('root')
);
```

---
## packages.json

1. dependencies
2. devDependencies
3. scripts

```bash
npm install --save react-color
npm install --save-dev chancejs
```

---
# [fit] Render component
```javascript
import React, { Component } from 'react';
import logo from './logo.svg';
import './App.css';

class App extends Component {
  render() {
    return (
      <div className="App">
        <div className="App-header">
          <img src={logo} className="App-logo" alt="logo" />
          <h2>Welcome to React</h2>
        </div>
        <p className="App-intro">
          To get started, edit <code>src/App.js</code> and save to reload.
        </p>
      </div>
    );
  }
}

export default App;
```
---

# [Fit] Development Tools
1. Webpack
  - Handling all assets
  - Leverage Import css/sass/image/svg
  - Post process 
2. Babel: translsate ES6 to ES5
3. Npm: npm start and npm build

---
## Let make a Button
# [fit] From Class component...

```javascript
import React from 'react';
class Button extends React.Component {
  render () {
    const {text, onClick} = this.props;
    return (
      <button onClick={onClick}>{text}</button>
    );
  }
}

export default Button;
```

---
## Let make a Button
# [fit] ... to Function component

```javascript
import React from 'react';

const Button = ({
  text,
  onClick
}) => {
  <button onClick={onClick}>{text}</button>
}

export default Button;
```

---
# Learning Resources

- [How to develop apps bootstrapped with Create React App.](https://github.com/facebookincubator/create-react-app/blob/master/packages/react-scripts/template/README.md)
- [Grommet getting start](https://grommet.github.io/docs/get-started)
- [React JS and why it's awesome](http://www.slideshare.net/AndrewHull/react-js-and-why-its-awesome)
- [Ecosystem](https://coggle.it/diagram/V-V9NDQLDIRs-ubT)

---

# What next?

- Lifecycle methods
- Props and State
- Routing
- Manage Application State with Mobx 
- Handle form
- Testing with Jest
- Styling & Responsive
