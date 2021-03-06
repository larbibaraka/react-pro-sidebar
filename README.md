# [React Pro Sidebar](https://www.npmjs.com/package/react-pro-sidebar)

[![npm][version]][npm-url]
[![License][license]][npm-url]
[![Peer][peer]][npm-url]

[version]: https://img.shields.io/npm/v/react-pro-sidebar.svg?style=flat-square
[license]: https://img.shields.io/github/license/azouaoui-med/react-pro-sidebar?style=flat-square
[peer]: https://img.shields.io/npm/dependency-version/react-pro-sidebar/peer/react?style=flat-square
[npm-url]: https://www.npmjs.com/package/react-pro-sidebar

React sidebar library with dropdown menus and unlimited number of nested submenus

## Demo

[Live preview](https://azouaoui-med.github.io/react-pro-sidebar)

## Installation

### yarn

```bash
yarn add react-pro-sidebar
```

### npm

```bash
npm install react-pro-sidebar
```

## Usage

```jsx
import { ProSidebar, Menu, MenuItem, SubMenu } from 'react-pro-sidebar';
import 'react-pro-sidebar/dist/css/styles.css';

<ProSidebar>
  <Menu iconShape="square">
    <MenuItem icon={<FaGem />}>Dashboard</MenuItem>
    <SubMenu title="Components" icon={<FaHeart />}>
      <MenuItem>Component 1</MenuItem>
      <MenuItem>Component 2</MenuItem>
    </SubMenu>
  </Menu>
</ProSidebar>;
```

If you are using sass then you can import the `styles.scss` directly into your scss file

```scss
@import '../node_modules/react-pro-sidebar/dist/scss/styles.scss';
```

## Custom Styling

There are sets of sass variables available which you can override to define your own styles

You need to include your override variables before importing the scss file

Your `custom.scss` file should look something like this

```scss
// Your variable overrides
$sidebar-bg-color: #1d1d1d;
$sidebar-color: #adadad;
$highlight-color: #d8d8d8;
$submenu-bg-color: #2b2b2b;
$submenu-bg-color-collapsed: #2b2b2b;
$icon-bg-color: #2b2b2b;
$icon-size: 35px;

@import '../node_modules/react-pro-sidebar/dist/scss/styles.scss';
```

## Using nested sub-menus

You can have as many nested menu-items and sub-menus as you like, and the syntax is very simple

```jsx
<Menu iconShape="square">
  <SubMenu title="Components" icon={<FaGem />}>
    <MenuItem>Component 1</MenuItem>
    <SubMenu title="Sub Component 1" icon={<FaHeart />}>
      {/* you can have more nested submenus ... */}
    </SubMenu>
  </SubMenu>
</Menu>
```

## Using React Router Dom

Here is an example on how to use [react router dom](https://github.com/ReactTraining/react-router) in the menu item

```jsx
import { Link } from 'react-router-dom';

<MenuItem icon={<FaGem />}>
  Dashboard
  <Link to="/" />
</MenuItem>;
```

## API

<table>
    <thead>
        <tr>
            <th>Component</th>
            <th>Prop</th>
            <th>Type</th>
            <th>Description</th>
            <th>Default</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan=4>ProSidebar</td>
            <td>collapsed</td>
            <td>boolean</td>
            <td>collapsed status of the sidebar </td>
            <td><code>false</code></td>
        </tr>
        <tr>
            <td>rtl</td>
            <td>boolean</td>
            <td>RTL direction</td>
            <td><code>false</code></td>
        </tr>
        <tr>
            <td>width</td>
            <td>number | string</td>
            <td>Width of the sidebar</td>
            <td><code>270px</code></td>
        </tr>
        <tr>
            <td>image</td>
            <td>string</td>
            <td>Url of the image to use in the sidebar background</td>
            <td>-</td>
        </tr>
         <tr>
            <td rowspan=1>Menu</td>
            <td>iconShape</td>
            <td>string</td>
            <td>Shape of the menu icons : <code>square</code> | <code>round</code> | <code>circle</code></td>
            <td>-</td>
        </tr>  
         <tr>
            <td rowspan=1>MenuItem</td>
            <td>icon</td>
            <td>ReactNode</td>
            <td>Icon for the menu item </td>
            <td>-</td>
        </tr>  
        <tr>
            <td rowspan=3>SubMenu</td>
            <td>title</td>
            <td>string | ReactNode</td>
            <td>Title for the submenu </td>
            <td>-</td>
        </tr>  
         <tr>
            <td>icon</td>
            <td>ReactNode</td>
            <td>Icon for submenu</td>
            <td>-</td>
        </tr>  
         <tr>
            <td>defaultOpen</td>
            <td>boolean</td>
            <td>Set if the submenu is open by default</td>
            <td><code>false</code></td>
        </tr>  
    </tbody>
</table>

## License

MIT © [Mohamed Azouaoui](https://azouaoui.netlify.com)
