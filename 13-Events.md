Ex1
```
import React, { Component } from 'react';
import ReactDOM from 'react-dom';


function Test(){ //Test Component
    const hello = () => { //arrow fun
        alert("Hello World");
    }

    function hi(){
        alert("Hi");
    }

    return <>
    <button onClick={hello}>Hello</button>
    <button onClick={hi}>Hi</button>
    </>;

}
const element = <Test/>

ReactDOM.render(element, document.getElementById('root'));
```
