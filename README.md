# React Boilerplate

It is well known project in React needs scaffolding, compiler configurations, bundlers, and linter setup.

This project presents a simple setup to get your React + Typescript project up and running.

## Popular Bootstraping Tools

### create-react-app

### Nextjs

## Manual boostraping approach

### Tech stack

- Package manager: [pnpm](https://pnpm.io/) (npm and yarn are just fine)

### Step-by-step

1. Create a `package.json`
   Run this command in the root folder:

```
pnpm init
```

This will make you go through a CLI configuration setup.

2. Create a `.gitignore`
   And add all files and folders that doesn't make sense to add to your remote repository, such as `node_modules` and `build`.

3. Install React libraries and Typescript
   If you need a specific version, add `@xx.xx` as sufix.

```
pnpm install react react-dom typescript --save
```

Don't forget to install the types library.

```
pnpm install @types/react-dom --save-dev
```

You still need to add a `tsconfig.json`. You can reference the one that is located in this repo.

4. Install transpilers (Babel)

```
pnpm install @babel/core @babel/preset-env @babel/preset-react @babel/preset-typescript --save-dev
```

Add also a configuration file or Babel, `.babelrc`:

```
{
  "presets": [
    "@babel/preset-env",
    "@babel/preset-react",
    "@babel/preset-typescript"
  ]
}
```

5. Install bundler (Webpack)

```
pnpm install webpack webpack-cli webpack-dev-server ts-loader babel-loader css-loader style-loader html-webpack-plugin --save-dev
```

You can also configure other bundlers, such as Parcel.

Now, you need to create and add configurations on the `webpack.config.js` file. You can check the one in this repo for referencing.

6. Script time!

Now, you need to add scripts into your `package.json` to speed up your environment.

```
"scripts": {
  "start": "webpack-dev-server --mode=development --open --hot",
  "build": "webpack --mode=production"
}
```

### Good to have

#### Linter and formatters

Linters help to flag and fix syntax issues. Formatters help maintain consistency throughout the codebase.

**Eslint**

First, install the linter (using Eslint in this case):

```
pnpm install eslint --save-dev
```

Then, start configuration with:

```
npx eslint --init
```

For it to work with Prettier, our chosen formatter, we need to install some extra Eslint configurations:

```
pnpm install eslint-config-prettier eslint-plugin-prettier prettier --save-dev
```

This is will make Eslint be responsible to make the formatting.

You can check the output file and additional configurations on the `.eslintrc.json`. Additionally, you can check `.prettierrc` for formatting configuration.

You still need to install Prettier extension on your editor for it to work, though.
