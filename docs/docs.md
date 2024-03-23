# React docs - Quick Start

> **Quick Links**: 
> [Table of contents](../contents.md) | [Previous: Installation](../notes/installation.md) | 

Now we have a running project, we obviously do not understand every line of it but we can start learning React JS concepts as well as practice them. Thus, it is time to go to React official documents.

On [React JS website](https://react.dev/), if we select `Learn`, we will land on [Quick Start](https://react.dev/learn) page. It starts with the following claim:

`Welcome to the React documentation! This page will give you an introduction to the 80% of React concepts that you will use on a daily basis.`

The goal of the chapter is listed as follow:

- How to create and nest components
- How to add markup and styles
- How to display data
- How to render conditions and lists
- How to respond to events and update the screen
- How to share data between components

Let's start with them.

## Before we start

Please start your local development server, if it is not already running, as follow:

```bash
cd src/react-vite
npm run dev
```

After that, open the URL `http://127.0.0.1:5173/` in the browser.

Now we should update our file `src\react-vite\src\App.jsx` as follow:

```jsx
import { useState } from 'react'

function App() {
  return (
    <div>
      <h1>Hello world! This is my first react app.</h1>
    </div>
  )
}

export default App
```

In this file, we just removed existing code, so that we get a clean slate to write the code we are going to learn in this section and beyond, while we are using this project.

### Updating the code without restarting dev-server.

We made the code changes but you may notice they are not reflected in the browser. Reason is, Vite is not looking if you modified the code. We may ask vite to check that.

Update your `src/react-vite/vite.config.js` file as follow:

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

We added the `server` section and asked Vite to `watch` change in the code using `usePolling: true`. After that, Vite will keep track if we make any change in any file and update the browser, without we restart the server.

However, for this change to take effect, we need to restart the server one last time. Press `Ctrl + c` to stop the server and run `npm run dev` again.

Open `http://127.0.0.1:5173/` again in the browser and you may see some ugly text. Don't worry, we will make it look good soon. But for now, try changing that text. Is that change updated in browser automatically? If yes, we are well set to just to the first section of the documentation.

> ### Version: `v3.0.0`
>
> Changes in the vite config can be seen on branch `v3.0.0`

