<!---
marp: true
theme: uncover
class: invert
headingDivider: 2
paginate: true
header: '&e tech'
footer: 'Created with [Marp](https://marp.app) and [Github Pages](https://pages.github.com)'
backgroundImage: 'img/react-logo.svg'
style: |
  header {
    height: 100px;
    width: 100px;
    float: left;
    background-color: #dfddd7;
    background-size: contain;
    -webkit-mask-image: url(img/and-e-tech-logo-300.svg);
    mask-image: url(img/and-e-tech-logo-300.svg);
    -webkit-mask-repeat: no-repeat;
    mask-repeat: no-repeat;
    -webkit-mask-size: contain;
    mask-size: contain;
    text-indent: -999999px
  }

  footer {
    font-size: 0.6rem;
  }
--->

# Component Lifecycle

* React components have a lifecycle with 3 phases:
* Mounting - triggered on creation of component and insertion into the DOM
* Updating - triggered when a component's props or state change
* Unmounting - triggered before the component is removed from the DOM
* Each phase has a number of methods we can use to hook into this lifecycle if we are using class components

# Component lifecycle - mounting

* Triggered on creation of component and insertion into the DOM
* Methods:
* `constructor(props)` - sets up initial state
* `getDerivedStateFromProps(props, state)` - called before rendering the DOM and sets state based on props
* `render()` - returns JSX which will be rendered as HTML in the DOM
* `componentDidMount()` - called after the DOM has rendered, often used to send requests to fetch data

# Component lifecycle - updating

* Triggered when a component's props or state changes
* Can occur multiple times
* Methods:
* `getDerivedStateFromProps(props, state)` - called before rendering the DOM and sets state based on props
* `shouldComponentUpdate(nextProps, nextState)` - decides wether the component should rerender, returns a boolean
* `render()` - returns JSX which will re rendered updated HTML in the DOM
* `getSnapshotBeforeUpdate(prevProps, prevState)` - called after render so you can see the previous state
* `componentDidUpdate(prevProps, prevState, snapshot)` - called after DOM updates, required if using `getSnapshotBeforeUpdate`, calling `setState` will cause render loop

# Component lifecycle - unmounting

* Triggered before the component is removed from the DOM
* Methods:
* `componentWillUnmount()` - used to cleanup after itself, once called the component is destroyed
