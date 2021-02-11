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

#### package.json

Add and run setup script.

```
mui": "npm install @material-ui/core @material-ui/icons",
dir": "cd public & rm *.png & cd ../src & rm logo.svg setupTests.js App.test.js index.css & mkdir components & cd ../",
setup": "npm run mui & npm run dir"
```

### 3. Create App Theme
