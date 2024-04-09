# React docs - Tic-Tec-Toe

> **Quick Links**: 
> [Table of contents](../contents.md) | [Previous: Docs](./docs.md) | 

These docs has been taken form [https://react.dev/learn/tutorial-tic-tac-toe]().

## Start new project

However, before we run them, we must have local running project. If you remember from [Installation](../notes/installation.md), we need to run following programs to create a new project

```bash
npx create-vite@latest tic-tac-toe --template react
cd tic-tac-toe
npm install
npm run dev
```

Only difference form installation is, we changed our project name from `react-vite` to `tic-tac-toe`.

Now open `http://127.0.0.1:5173/` in browser to load the page.

Also as mentioned in the section `Updating the code without restarting dev-server.` of [React docs - Quick Start](./docs.md), we need to update `src/tic-tac-toe/vite.config.js` as follow so that changes are reflected in the browser without restarting local server.

```js
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'

// https://vitejs.dev/config/
export default defineConfig({
  plugins: [react()],
  server: {
    watch: {
      usePolling: true
    }
  }
})
```

To make sure changes are reflected, change `<h1>Vite + React</h1>` to `<h1>Tic Tac Toe</h1>` in `src/tic-tac-toe/src/App.jsx`. It should be reflected in the browser as soon as you save the file, without restarting the server.

## Setup Tic-tac-toe

When we create a React project with Vite, it give some basic code. However for our project, or any new project in future, we need to clear that code. Let's first clear what we got with Vite

**App.jsx**

We do not need React and Vite logo, let's delete these lines

```jsx
import reactLogo from './assets/react.svg'
import viteLogo from '/vite.svg'
```

We also don't need state for now, wet's remove that too.

Our App.jsx now looks like:

```jsx
import { useState } from 'react'
import './App.css'

function App() {
  return (
    <>
      <div>Tic Tac Toe</div>
    </>
  )
}

export default App
```

We may notice our Tic Tac Toe is there in the center of the page. This is because we are still loading vite CSS. Let's devete everything from app.css and index.css.

Looks Good! Well, design may not be looking good right now, but we have a clean slate now to start working on out Tic Tac toe.

We are now ready for our Tic-tac-Toe tutorial from official react docs.

## Tic Tac Toe from official docs.

Official docs link: [https://react.dev/learn/tutorial-tic-tac-toe]()

Official docs start with What we will be building. We can skip that section for now or you can head towards official docs and check what we will be building.

Here, we are more interested in code so let's dive into code.

### Section: setup the tutorial

In this section, we are trying to make the square with `X` written on it. Let's update App.jsx as mentioned in the tutorial

```jsx
export default function Square() {
  return <button className="square">X</button>;
}
```

When we save it, we get a box (button) with X written on it but is seems smaller. Let's copy following CSS from sandbox and add it to our index.css

```css
* {
  box-sizing: border-box;
}

body {
  font-family: sans-serif;
  margin: 20px;
  padding: 0;
}

h1 {
  margin-top: 0;
  font-size: 22px;
}

h2 {
  margin-top: 0;
  font-size: 20px;
}

h3 {
  margin-top: 0;
  font-size: 18px;
}

h4 {
  margin-top: 0;
  font-size: 16px;
}

h5 {
  margin-top: 0;
  font-size: 14px;
}

h6 {
  margin-top: 0;
  font-size: 12px;
}

code {
  font-size: 1.2em;
}

ul {
  padding-inline-start: 20px;
}

* {
  box-sizing: border-box;
}

body {
  font-family: sans-serif;
  margin: 20px;
  padding: 0;
}

.square {
  background: #fff;
  border: 1px solid #999;
  float: left;
  font-size: 24px;
  font-weight: bold;
  line-height: 34px;
  height: 34px;
  margin-right: -1px;
  margin-top: -1px;
  padding: 0;
  text-align: center;
  width: 34px;
}

.board-row:after {
  clear: both;
  content: '';
  display: table;
}

.status {
  margin-bottom: 10px;
}
.game {
  display: flex;
  flex-direction: row;
}

.game-info {
  margin-left: 20px;
}
```

Let's not dive into CSS for now. You can read it, it is straight forward. If you are unable to understand css, do some basic CSS tutorial or google the part you are not able to understand. Let's keep our focus on react for now and let's dive into our App component

Our Square component is straight forward, no JS code, it is simple returning JSX with a button and css class `square` applied on it.

### index.js

In the React tutorial or code sandbox, you will find the file `index.js`, equivalent file in our code is `main.jsx`. At a first glance, index.js or main.jsx may look different, but at a closer look, they are similar, let's check them

In index.js, line 1 import StrictMode from react so they used `<StrictMode>` while rendering. Main.jsx didn't import it sop used React.StrictMode. Same is the case with ReactDOM; index.js directly imported createRoot but main.jsx imported ReactDOM and hance used ReactDOM.createRoot. So our app created from vite is slightly differect in the code, but if we check details, it is exactly same code.

### Section: building the board

In this section, it is explained step byu step, how to build the board.

It started with adding two buttons on the Square like

```jsx
export default function Square() {
  return <button className="square">X</button><button className="square">X</button>;
}
```

However, it throws error as react can return only one tag and we are returning two `<button>` tags. ti fix it, we wrap our code in empty JSX fragment `<> </>`.

```jsx
export default function Square() {
  return (
    <>
      <button className="square">X</button>
      <button className="square">X</button>
    </>
  );
}
```

We can copy-paste button 9 times to get 9 buttons. However, on the board, we have to make 3x3 board. CSS class `board-row` is already available in our CSS. We can update the Square component as follow to get the initial board.

```jsx
export default function Square() {
  return (
    <>
      <div className="board-row">
        <button className="square">1</button>
        <button className="square">2</button>
        <button className="square">3</button>
      </div>
      <div className="board-row">
        <button className="square">4</button>
        <button className="square">5</button>
        <button className="square">6</button>
      </div>
      <div className="board-row">
        <button className="square">7</button>
        <button className="square">8</button>
        <button className="square">9</button>
      </div>
    </>
  );
}
```

This is simple CSS and will give us required initial board of Tic Tac Tow, with hardcoded numbers.

We now have a problem. Our Square component is no longer a Square but a board. Let's fix it:

```jsx
function Square() {
  return <button className="square">X</button>;
}

export default function Board() {
  return (
    <>
      <div className="board-row">
        <Square />
        <Square />
        <Square />
      </div>
      <div className="board-row">
        <Square />
        <Square />
        <Square />
      </div>
      <div className="board-row">
        <Square />
        <Square />
        <Square />
      </div>
    </>
  );
}
```

We moved most of the code in Board component. We also created a new component Square and called it within Board to display the Square button. Next problem now is, all button have texty 'X'. Our Board component should ideally pass that value. We can use props for that. We learned in section `Sharing data between components` of [Previous topic: Docs](./docs.md)

```jsx
function Square({ value }) {
  return <button className="square">{value}</button>;
}

export default function Board() {
  return (
    <>
      <div className="board-row">
        <Square value="1" />
        <Square value="2" />
        <Square value="3" />
      </div>
      <div className="board-row">
        <Square value="4" />
        <Square value="5" />
        <Square value="6" />
      </div>
      <div className="board-row">
        <Square value="7" />
        <Square value="8" />
        <Square value="9" />
      </div>
    </>
  );
}
```

That was an example of `props`, where parent component send data to the child component.

We need two more things, managing stage and sending data from child component to parent component (events). In the React tutorial, we first manage state at child level (In Square component). Initially, there must be no text and upcon clicking the button, it should have `X`. That should be simple if you remember the section `Sharing data between components` from the [Previous topic: Docs](./docs.md)

```jsx
import { useState } from 'react';

function Square() {
  const [value, setValue] = useState(null);

  function handleClick() {
    setValue('X');
  }

  return <button className="square" onClick={handleClick}>{value}</button>;
}

export default function Board() {
  return (
    <>
      <div className="board-row">
        <Square />
        <Square />
        <Square />
      </div>
      <div className="board-row">
        <Square />
        <Square />
        <Square />
      </div>
      <div className="board-row">
        <Square />
        <Square />
        <Square />
      </div>
    </>
  );
}
```

**What we changed?** We first import useStage hook from react and used it on `value`. With this, we also need function `handleClick` to set the value. We called that function `onClick` of our Button. In the board component, we now no longet need to pass the value so removed it.

> ### Version: `v4.1.0`
>
> Code demonstrating useState hook in Tic Tac Toe `v4.1.0`
