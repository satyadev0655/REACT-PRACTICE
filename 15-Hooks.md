Example-1

```
import React, { useState } from 'react';
import ReactDOM from 'react-dom';


function Example() {
  // Declare a new state variable, which we'll call "count"
  const [name, setName] = useState("");

  return (
    <div>
      <p>My Name is {name}</p>
      <button onClick={() => setName("Alex")}>
        Click me
      </button>
    </div>
  );
}
const element = <Example/>

ReactDOM.render(element, document.getElementById('root'));
```

//Ex-3
```
import React, { useState } from 'react';
import ReactDOM from 'react-dom';


function Example() {
  // Declare a new state variable, which we'll call "count"
  const [name, setName] = useState("");
  const [email, setEmail] = useState("");
  const [address, setAddress] = useState("");

  const changeCName = (e) =>{
    console.log(e.target.value);
    setName(e.target.value)
  }

  return <>
  Name : {name}

        <form onSubmit={(e) => {formSubmit(e)}}>
            <label>Company Name</label>
            <input type="text" name="cname" onChange={changeCName}/> <br/>

            <label>Company Email</label>
            <input type="text" name="cemail"/> <br/>

            <label>Company Address</label>
            <input type="text" name="caddres"/> <br/>
            <input type="submit" value="Save"/>
        </form>
    </>;
}
const element = <Example/>

ReactDOM.render(element, document.getElementById('root'));
```


Ex-4
```
import React, { useState } from 'react';
import ReactDOM from 'react-dom';


function Example() {
  // Declare a new state variable, which we'll call "count"
  const [name, setName] = useState("");
  const [email, setEmail] = useState("");
  const [address, setAddress] = useState("");

  const updateForm = (e) =>{
    let fieldName = e.target.name;

    if(fieldName == "cname"){
        setName(e.target.value);
    }

    else if(fieldName == "cemail"){
        setEmail(e.target.value);
    }

    else if(fieldName == "caddres"){
        setAddress(e.target.value);
    }

    //console.log(e.target.name);
    //setName(e.target.value)
  }

  return <>
  Name : {name}, Email : {email}

        <form onSubmit={(e) => {formSubmit(e)}}>
            <label>Company Name</label>
            <input type="text" name="cname" onChange={updateForm}/> <br/>

            <label>Company Email</label>
            <input type="text" name="cemail" onChange={updateForm}/> <br/>

            <label>Company Address</label>
            <input type="text" name="caddres" onChange={updateForm}/> <br/>
            <input type="submit" value="Save"/>
        </form>
    </>;
}
const element = <Example/>

ReactDOM.render(element, document.getElementById('root'));
```


import React, { useState } from 'react';
import ReactDOM from 'react-dom';


function Example() {
    const[company, setCompanyInfo] =  useState({
        name: '',
        email: '',
        address: ''
    })

  const updateForm = (e) =>{
   setCompanyInfo({
    ...company,[e.target.name] : e.target.value
   });
   //we will use Spread operator to pass the current company object data and update the respective element value
   //https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax
  }

  return <>
  Name : {company.name}, Email : {company.email}

        <form onSubmit={(e) => {formSubmit(e)}}>
            <label>Company Name</label>
            <input type="text" name="name" onChange={updateForm}/> <br/>

            <label>Company Email</label>
            <input type="text" name="email" onChange={updateForm}/> <br/>

            <label>Company Address</label>
            <input type="text" name="addres" onChange={updateForm}/> <br/>
            <input type="submit" value="Save"/>
        </form>
    </>;
}
const element = <Example/>

ReactDOM.render(element, document.getElementById('root'));
