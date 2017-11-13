# react-scripts-cssmodules

Adds [CSS Modules](https://github.com/css-modules/css-modules) to [Create React App](https://github.com/facebookincubator/create-react-app).

## How to use
Either create a new project using
`create-react-app my-app --scripts-version react-scripts-cssmodules`
or within your existing project uninstall `react-scripts` and install `react-scripts-cssmodules`.

## Using CSS and CSS Modules
To import as regular css, do the same as in CRA. `import mystyles.css`
To import as css modules, rename the file to `[name].module.css` and the use as normal css modules.

## Example
### `Button.module.css`

```css
.button {
  padding: 20px;
}
```

### `another-stylesheet.css`

```css
.button {
  color: green;
}
```

### `Button.js`

```js
import React, { Component } from 'react';
import './another-stylesheet.css'; // Import regular stylesheet
import styles from './Button.module.css'; // Import css modules stylesheet as styles

class Button extends Component {
  render() {
    // You can use them as regular CSS styles
    return <div className={styles.button} />;
  }
}
```
### `exported HTML`
No clashes from other `.button` classnames

```html
<div class="src__Button-module___button"></div>
```

## Versioning
This package is 10:1 with Create React App. E.g. v0.9.10 of this package is the same as and interchanable with v0.9.1 of Create React App.

Any additional numbers are fixes for this app only. E.g. v0.9.21 is v0.9.2 of React App with a fix only for cssmodules.

See this [CRA Issue](https://github.com/facebookincubator/create-react-app/issues/682) for more details, or for a more indepth guide check out [this article](https://medium.com/@shubheksha/tweaking-configuration-for-react-scripts-in-create-react-app-d91e9d03a42f).
