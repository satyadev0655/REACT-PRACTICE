Ex-1
```
import React, { useState, useEffect } from 'react';
import ReactDOM from 'react-dom';

const AppContext = React.createContext({
  data: ''
});

class Container extends React.Component {
  constructor(props){
    super(props);
    this.state = {
     data:{
      name: "Alex",
      email: "alex@test.com"
     }
    }
  }
  render() {
    return (
      <AppContext.Provider value={this.state.data}>
        <A /> <B/>
      </AppContext.Provider>
    );
  }
}

class A extends React.Component {
  static contextType = AppContext;
  render() {
    return <h1> {this.context.name} </h1>;
  }
}

class B extends React.Component {
  static contextType = AppContext;
  render() {
    return <h1> {this.context.email} </h1>;
  }
}


const element = <Container/>;
ReactDOM.render(element, document.getElementById('root'));

```
