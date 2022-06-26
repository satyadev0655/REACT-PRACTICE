Ex-1 Mounting
```
import React, { useState, useEffect } from 'react';
import ReactDOM from 'react-dom';


class A extends React.Component{
  constructor(props){
    super(props);
    this.state = {name : "Alex", email: ""};
    console.log("1 Constructor called");
  }

  static getDerivedStateFromProps(props, state){
    console.log("2 getDerivedStateFromProps called");
    return {name: props.pname}
  }

  componentDidMount(){
    console.log("2 getDerivedStateFromProps called");
    setTimeout(()=>{
        this.setState({email:"david@test.com"})
    },1000);
    console.log("4 componentDidMount called");
  }
  
  render(){
    console.log("3 render called");
    return(
    <>
   <h1>{this.state.name}</h1>
   <p>{this.state.email}</p>

    </>
    );
  }
}

const element = <A pname="Benn"/>;
ReactDOM.render(element, document.getElementById('root'));

```
