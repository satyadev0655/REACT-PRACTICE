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


Ex2: Passing arguments
```
import React, { Component } from 'react';
import ReactDOM from 'react-dom';


function Test(){ //Test Component
    const hello = (msg) => { //arrow fun
        alert(msg);
    }

    return <>
    <button onClick={()=>hello("heloworld")}>Hello</button>
    </>;

}
const element = <Test/>

ReactDOM.render(element, document.getElementById('root'));
```


Ex-3 React Event Object
```
import React, { Component } from 'react';
import ReactDOM from 'react-dom';


function Test(){ //Test Component
    const hello = (msg, event) => { //arrow fun
        event.preventDefault();
        console.log(event);
    }

    return <>
    <button onClick={(e)=>hello("heloworld",e)}>Hello</button>
    <button onDoubleClick={(e)=>hello("heloworld",e)}>Hello</button>
    </>;

}
const element = <Test/>

ReactDOM.render(element, document.getElementById('root'));
```
