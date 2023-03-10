<!---
marp: true
theme: gaia
class: invert
headingDivider: 2
paginate: true
header: '&e tech'
footer: 'Created with [Marp](https://marp.app) and [Github Pages](https://pages.github.com)'
backgroundImage: 'img/react-logo.svg'
style: |
  :root {
    --color-background: ##202228;
  }

  section {
    font-size: 30px;
  }

  section header {
    height: 100px;
    width: 100px;
    left: auto;
    right: 40px;
    background-color: #dfddd7;
    background-size: contain;
    -webkit-mask-image: url(img/and-e-tech-logo-300.svg);
    mask-image: url(img/and-e-tech-logo-300.svg);
    -webkit-mask-repeat: no-repeat;
    mask-repeat: no-repeat;
    -webkit-mask-size: contain;
    mask-size: contain;
    text-indent: -99999999px
  }
--->

# Introduction

* Pre React 16.8, functional components do not have state
* Instead we have to use class components to add state
* Post React 16.8 we can use something called "hooks" to add state to functional components
* Hooks dont just cover state, they cover lifecycle events and other features too
* This simplifies our components

# Component Lifecycle

* React components have a lifecycle with 3 phases:
* Mounting - triggered on creation of component and insertion into the DOM
* Updating - triggered when a component's props or state change
* Unmounting - triggered before the component is removed from the DOM
* Each phase has a number of methods to hook into lifecycle events

# Component lifecycle - mounting

* Triggered on creation of component and insertion into the DOM
* Methods:
* `constructor(props)` - sets up initial state
* `getDerivedStateFromProps(props, state)` - sets state from props before rendering DOM
* `render()` - returns JSX to be rendered into the DOM
* `componentDidMount()` - called after the DOM has rendered

# Component lifecycle - updating

* Triggered when a component's props or state changes and can occur more than once
* Methods:
* `getDerivedStateFromProps(props, state)` - sets state from props before rendering DOM
* `shouldComponentUpdate(nextProps, nextState)` - decides wether the component should rerender
* `render()` - returns JSX to be re rendered and update the DOM
* `getSnapshotBeforeUpdate(prevProps, prevState)` - called after render so you can see the previous state
* `componentDidUpdate(prevProps, prevState, snapshot)` - called after DOM updates

# Component lifecycle - unmounting

* Triggered before the component is removed from the DOM
* Methods:
* `componentWillUnmount()` - used to cleanup after itself, once called the component is destroyed
