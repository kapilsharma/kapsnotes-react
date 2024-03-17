# Installation

> **Quick Links**: 
> [Table of contents](../contents.md) | [Previous: About KAPsNotes - React JS](../README.md) | [Next: Official docs](../docs/docs.md)

As discussed on previous topic, we need to code and code a lot. For this, we need a react project running locally. I mostly prefer to go to the official documentation and [React official documentation](https://react.dev/learn/installation) suggest using [Next.js application](https://react.dev/learn/start-a-new-react-project)

As an exception in React's case, I wont personally recommend that. Next.JS is both frontend and backend combined. If you are interested only in frontend, don't commit yourself to Next.js.

This is the case with me as well, I mostly use [Laravel (PHP)](https://laravel.com/) or [NodeJS (Java Script)](https://nodejs.org/en) in the backend so Next.js is not an option for me, at least in my current official projects.

## Vite vs Create React App

In Java Script world, there are some bootstrap tools, which help us creating JS application. For React, most popular options are [Vite](https://vitejs.dev/guide/) and [Create react app](https://create-react-app.dev/)

They both are excellent tools, catering to different preferences and project requirements.

- Create React App is good for quick start, ease of use, and having conventional structure. However, it is there since long and showing its age, specially for going live.
- Vite support not only react but also other libraries. It have both JavaScript and TypeScript support, fast development speed and optimized for production.

For the decision, it depends the tool used by your other team members but if you can decide, I'd recommend to go with Vite.

If you decide using Create react app, you may start the project as mentioned in their [docs](https://create-react-app.dev/docs/getting-started).

In these notes, I'm choosing Vite as it is my personal preference.

## Creating React application using Vite

> **Prerequisite:** You must have NodeJS (and NPM) installed.

- Clone the repo.
  - `git clone git@github.com:kapilsharma/kapsnotes-react.git`
- Go to `src` folder: `cd src`.
- Run the command `npx create-vite@latest react-vite --template react`. You can change the name of project `react-vite` as per your preference, `react-vite` is already present in the repo.

```bash
npx create-vite@latest react-vite --template react
Need to install the following packages:
create-vite@5.2.1
Ok to proceed? (y)

Scaffolding project in /mnt/c/Users/kapil/dev/git/kapilsharma/kapsnotes-react/src/react-vite...

Done. Now run:

  cd react-vite
  npm install
  npm run dev

npm notice
npm notice New minor version of npm available! 10.2.3 -> 10.5.0
npm notice Changelog: https://github.com/npm/cli/releases/tag/v10.5.0
npm notice Run npm install -g npm@10.5.0 to update!
npm notice
```

It will create the react application. We can now run following cocommands to run the local development server.

```bash
cd react-vite
npm install
npm run dev
```

I'll not go into details of npm commands, please read about it to know more.

After running `npm run dev`, we will see output something like that

```bash
 VITE v5.1.5  ready in 2267 ms

  ➜  Local:   http://localhost:5173/
  ➜  Network: use --host to expose
  ➜  press h + enter to show help
```

Please check the URL against Local. For me, its `http://localhost:5173/`. Open browser and enter that URL

## Understanding new project

If we check react-vite folder, it have following files. Let's check them one by one.

```bash
react-vite
├── README.md
├── index.html
├── package-lock.json
├── package.json
├── public
│   └── vite.svg
├── src
│   ├── App.css
│   ├── App.jsx
│   ├── assets
│   │   └── react.svg
│   ├── index.css
│   └── main.jsx
├── vite.config.js
└── node_modules
```

- `README.md` is project's default READMD file, that you can edit as per project requirements.
- `index.html` is the main starting point, that we will see in a while.
- `package.json` and `package-lock.json` are npm files, I hope you understand.
- `public` folder contains the files that we want to serve to the browser, They cenerally contains images, fonts etc.
- `src` is the main source folder for our reach app, we will check it later.
- `vite.config.js` is vite configuration file that we can skip for now.
- `node_modules` contains third-party libraries that we install through npm. We can skip them for now.

Main code starts with index.html, which have following code.

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <link rel="icon" type="image/svg+xml" href="/vite.svg" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Vite + React</title>
  </head>
  <body>
    <div id="root"></div>
    <script type="module" src="/src/main.jsx"></script>
  </body>
</html>
```

It is normal HTML and head section. However, body tag looks different. It is main div with id as `root`. This is where React will do its magic. And then we imported `main.jsx` file, which is our main react application.

Now we can see what is there in main.jsx file.

```jsx
import React from 'react'
import ReactDOM from 'react-dom/client'
import App from './App.jsx'
import './index.css'

ReactDOM.createRoot(document.getElementById('root')).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
)
```

- In first two lines, we import `React` and `ReactDOM` from ReactJS library. We will learn more aboout them soon.
- In next line, we import `App`, from `App.jsx`, which is our root level React component and we do write code for it. We will learn about it in details in the next chepter, while learning about react components.
- Then we included our CSS file. I won't go into CSS and hope you know about HTML and CSS.
- The next line `ReactDOM.createRoot` does the main magic. Well, its not magic once you understand React but for now, let's take that as magic. It need a HTML DOM element to work with and we are passing our div with id `root` as the element for react to work with. After that, it calls `render` method to actually filll the tag. Input for render method is JSX, that we will discuss in details in next chapter but in short, you cna consider as HTML with some custom tags.
- The first tag is [React.StrictMode](https://react.dev/reference/react/StrictMode), which helps us find issues and error during development. We can skip it too for now.
- And at last, we have `<App />`, our custom react component.

Code of `<app />` is given in `src/App.jsx` but let's not dive into it immediately. We will start learning about reach components from the next chapter.

> ### Version: `v1.0.0`
> Basic project installation can be seen on branch `v1.0.0`

> **Quick Links**: 
> [Table of contents](../contents.md) | [Previous: About KAPsNotes - React JS](../README.md) | [Next: Official docs](../docs/docs.md)
