<div align="center">
<h1>React Boilerplate</h1>
</div>

## Web Apps

<details>

<summary><b>CRA</b></summary>

### 1. Initialize Create React App

```sh
$ npx create-react-app my-app
```

### 2. Install Material UI and Setup Directories

With PowerShell:

```json
"mui": "npm install @material-ui/core @material-ui/icons",
"del": "del public\\*.png, src\\logo.svg, src\\setupTests.js, src\\App.test.js, src\\index.css",
"dir": "mkdir src\\components",
"setup": "npm run mui & npm run del & npm run dir"
```

With Bash:

```json
"mui": "npm install @material-ui/core @material-ui/icons",
"del": "rm public/*.png src/logo.svg src/setupTests.js src/App.test.js src/index.css",
"dir": "cd src && mkdir components",
"setup": "npm run mui & npm run del & npm run dir"
```

### 3. Create App Theme and Add Styles

index.js

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
            main: "#267fa6",
        },
        secondary: {
            main: "#eb7628",
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
        fontFamily: ["Lato", "Roboto", "Helvetica", "Arial", "sans-serif"].join(","),
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

App.js

```js
import React from "react";
import { makeStyles } from "@material-ui/core/styles";
import { Typography } from "@material-ui/core";
import "./App.css";

const useStyles = makeStyles((theme) => ({
    headerTitle: {
        background: theme.palette.primary.main,
        borderBottom: `0.5rem solid ${theme.palette.secondary.main}`,
        textAlign: "center",
        padding: "2rem 0",
    },
}));

function App() {
    const classes = useStyles();
    return (
        <div className={classes.root}>
            <main className={classes.main}>
                <Typography variant="h3" component="h1" className={classes.headerTitle}>
                    Create React App
                </Typography>
            </main>
        </div>
    );
}

export default App;
```

App.css

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

</details>

<details>

<summary><b>CRA + TypeScript</b></summary>

### 1. Initialize Create React App

```sh
$ npx create-react-app my-app --template typescript
```

### 2. Install Material UI and Setup Directories

With PowerShell:

```json
"mui": "npm install @material-ui/core @material-ui/icons",
"del": "del public\\*.png, src\\logo.svg, src\\setupTests.ts, src\\App.test.tsx, src\\index.css",
"dir": "mkdir src\\components",
"setup": "npm run mui & npm run del & npm run dir"
```

With Bash:

```json
"mui": "npm install @material-ui/core @material-ui/icons",
"del": "rm public/*.png src/logo.svg src/setupTests.ts src/App.test.tsx src/index.css",
"dir": "cd src && mkdir components",
"setup": "npm run mui & npm run del & npm run dir"
```

### 3. Create App Theme and Add Styles

index.tsx

```tsx
import React from "react";
import ReactDOM from "react-dom";
import { createMuiTheme } from "@material-ui/core/styles";
import { ThemeProvider } from "@material-ui/styles";
import App from "./App";
import reportWebVitals from "./reportWebVitals";

const theme = createMuiTheme({
    palette: {
        primary: {
            main: "#267fa6",
        },
        secondary: {
            main: "#eb7628",
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
        fontFamily: ["Lato", "Roboto", "Helvetica", "Arial", "sans-serif"].join(","),
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

App.tsx

```tsx
import React from "react";
import { makeStyles } from "@material-ui/core/styles";
import { Typography } from "@material-ui/core";
import "./App.css";

const useStyles = makeStyles((theme) => ({
    root: {},
    main: {},
    headerTitle: {
        background: theme.palette.primary.main,
        borderBottom: `0.5rem solid ${theme.palette.secondary.main}`,
        textAlign: "center",
        padding: "2rem 0",
    },
}));

function App() {
    const classes = useStyles();
    return (
        <div className={classes.root}>
            <main className={classes.main}>
                <Typography variant="h3" component="h1" className={classes.headerTitle}>
                    Create React App
                </Typography>
            </main>
        </div>
    );
}

export default App;
```

App.css

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

</details>
