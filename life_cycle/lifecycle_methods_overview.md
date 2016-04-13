# React Life Cycle Methods Overview
  Not all UI systems implement or follow the life cycle concept. Some systems implement there own process or use different concepts. This doesn't make libraries that use a life cycle better or worse, it just defines the process we can take advantage of.
  
  Because React does follow this pattern, the development team provides a series of hooks we can tap into. These method hooks inform us of where the component is in the life cycle and what we can and cannot do.
  
  Each of the life cycle methods are called in a specific order and at a specific time. The methods are also tied to different parts of the Life Cycle. Here are the methods broken down in order and by their corresponding life cycle phase [^1]:
  
## Birth / Mounting
1. Initialize / Construction
2. `getDefaultProps()` *(React.createClass)* or `MyComponent.defaultProps` *(ES6 class)*
3. `getInitialState()` *(React.createClass)* or `this.state = ...` *(ES6 constructor)*
4. `componentWillMount()`
5. `render()`
6. Children initialization & life cycle kickoff
7. `componentDidMount()`
  
## Growth / Update
1. `componentWillRecieveProps()`
2. `shouldComponentUpdate()`
3. `render()`
4. Children Life cycle methods
5. `componentWillUpdate()`

## Death / UnMounting
1. `componentWillUnmount()`
4. Children Life cycle methods
5. Instance destroyed for Garbage Collection

The order of these methods are strict and are called as defined above. Most of the time is spent in the Growth/Update phase and those methods are called many times. The Birth and Death methods will only be called once.

[^1] *Most of the methods are the same if you use either `React.createClass` or using ES6 classes, such as `class MyComponent extends React.Component`. A few are different, mainly around how instantiation/creation occurs. We will call these differences out throught the chapter.*