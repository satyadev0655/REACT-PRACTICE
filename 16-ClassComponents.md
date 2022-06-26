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


Ex-2 : Updating
```
import React, { useState, useEffect } from 'react';
import ReactDOM from 'react-dom';


class A extends React.Component{
  constructor(props){
    super(props);
    this.state = {name : "Alex", email: "alex@test.com"};
  }

  static getDerivedStateFromProps(props, state){
    console.log("1 getDerivedStateFromProps called");
    return {name: props.pname}
  }

  componentDidMount(){
    setTimeout(()=>{
        this.setState({email:"david@test.com"})
    },1000);
    
  }

  shouldComponentUpdate(){
    console.log("2 shouldComponentUpdate called");
    return true;
  }

  getSnapshotBeforeUpdate(prevProps, prevState){
    console.log("4 getSnapshotBeforeUpdate called");
    console.log("prev state value : " + prevState.email);
    return null;
  }


  componentDidUpdate(){
    console.log("5 componentDidUpdate called");
    console.log("update state value : " + this.state.email);
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


Ex-3 Unmount

import React, { useState, useEffect } from 'react';
import ReactDOM from 'react-dom';

class PopupWindow extends React.Component{
  componentWillUnmount(){
    console.log("componentWillUnmount called");
  }
  render(){
    return(
    <>
    <h1>Popup Window</h1>
    </>
    );
  }
}
class DisplayList extends React.Component{
  constructor(props){
    super(props);
    this.state = {showPopupFlag : false};
  }

  showPopup = () => {
    this.setState({showPopupFlag : true})
  }

  hidePopup = () => {
    this.setState({showPopupFlag : false})
  }

  
  render(){
    let pElement;
    if(this.state.showPopupFlag){
      pElement = <PopupWindow/>
    }

    return(
    <>
    {pElement}
    <button onClick={this.showPopup}>Show Popup</button>
    <button onClick={this.hidePopup}>Hide Popup</button>

    </>
    );
  }
}

const element = <DisplayList/>;
ReactDOM.render(element, document.getElementById('root'));

