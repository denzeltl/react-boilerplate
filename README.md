# React Boilerplate

## React Apps

### 1. Initialize Create React App

#### Standard CRA

```
npx create-react-app my-app
```

#### With TypeScript

```
npx create-react-app my-app --template typescript
```

### 2. Install Material UI and Setup Directories

#### With Bash

```json
"mui": "npm install @material-ui/core @material-ui/icons",
"dir": "rm public/*.png src/logo.svg src/setupTests.js src/App.test.js src/index.css & mkdir src/components",
"setup": "npm run mui & npm run dir",
```

#### With PowerShell

```json
"mui": "npm install @material-ui/core @material-ui/icons",
"dir": "del public\\*.png, src\\logo.svg, src\\setupTests.js, src\\App.test.js, src\\index.css",
"com": "mkdir src\\components",
"setup": "npm run mui & npm run dir & npm run com"
```

### 3. Create App Theme and Add Styles

#### index.js

```js
import React from "react";
import ReactDOM from "react-dom";
import { createMuiTheme } from "@material-ui/core/styles";
import { ThemeProvider } from "@material-ui/styles";
import App from "./App";
import reportWebVitals from "./reportWebVitals";

const theme = createMuiTheme({
    palette: {
        primary: {
            main: "#1f7cbf",
        },
        secondary: {
            main: "#e88d25",
        },
        success: {
            main: "#42b347",
        },
        error: {
            main: "#ef4a4a",
        },
        background: {
            default: "#ffffff",
        },
    },
    typography: {
        fontFamily: ["Lato", "Roboto", "Helvetica", "Arial", "sans-serif"].join(
            ","
        ),
    },
    breakpoints: {
        values: {
            xs: 0,
            sm: 480,
            md: 768,
            lg: 992,
            xl: 1200,
        },
    },
});

ReactDOM.render(
    <ThemeProvider theme={theme}>
        <App />
    </ThemeProvider>,
    document.getElementById("root")
);

// If you want to start measuring performance in your app, pass a function
// to log results (for example: reportWebVitals(console.log))
// or send to an analytics endpoint. Learn more: https://bit.ly/CRA-vitals
reportWebVitals();
```

#### App.css

```css
* {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
}

* ::-moz-selection {
    background: #eb431d;
    color: #fff;
}

* ::selection {
    background: #eb431d;
    color: #fff;
}

html {
    font-size: 16px;
}

body {
    font-family: inherit;
    background: #fff;
    color: #222;
}

input,
select,
textarea,
button {
    font-family: inherit;
}

button {
    background: transparent;
    outline: 0;
    border: 0;
    cursor: pointer;
}

ul {
    list-style: none;
}

a {
    color: #222;
    text-decoration: none;
}
```
