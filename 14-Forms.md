```
import React, { Component } from 'react';
import ReactDOM from 'react-dom';


function Test(){ //Test Component
    const formSubmit = (event) => { //arrow fun
        event.preventDefault();
        //console.log(event);
        //console.log(event.target.elements.cname.value) // from elements property
        //console.log(event.target.cname.value)          // or directly

        let cname = event.target.elements.cname.value;
        let cemail = event.target.elements.cemail.value;
        let caddress = event.target.elements.caddres.value;

        const payload = {
            cname :event.target.elements.cname.value,
            cemail : event.target.elements.cemail.value,
            caddress : event.target.elements.caddres.value
        }

        console.log(payload);

        //Fetch API Post    
        //http://app1.dev-app.cf/api/v1/companies

    }

    return <>
        <form onSubmit={(e) => {formSubmit(e)}}>
            <label>Company Name</label>
            <input type="text" name="cname"/> <br/>

            <label>Company Email</label>
            <input type="text" name="cemail"/> <br/>

            <label>Company Address</label>
            <input type="text" name="caddres"/> <br/>
            <input type="submit" value="Save"/>
        </form>
    </>;

}
const element = <Test/>

ReactDOM.render(element, document.getElementById('root'));

```


```
import React, { Component } from 'react';
import ReactDOM from 'react-dom';


function Test(){ //Test Component
    const formSubmit = (event) => { //arrow fun
        event.preventDefault();
        //console.log(event);
        //console.log(event.target.elements.cname.value) // from elements property
        //console.log(event.target.cname.value)          // or directly

        let cname = event.target.elements.cname.value;
        let cemail = event.target.elements.cemail.value;
        let caddress = event.target.elements.caddres.value;

        const payload = {
            name :event.target.elements.cname.value,
            email : event.target.elements.cemail.value,
            address : event.target.elements.caddres.value
        }

        console.log(payload);

        //Fetch API Post    
        //http://app1.dev-app.cf/api/v1/companies
       //const data = { username: 'example' };

            fetch('http://app1.dev-app.cf/api/v1/companies', {
            method: 'POST', // or 'PUT'
            headers: {
                'Content-Type': 'application/json',
            },
            body: JSON.stringify(payload),
            })
            .then(response => response.json())
            .then(data => {
            console.log('Success:', data);
            })
            .catch((error) => {
            console.error('Error:', error);
            });

    }

    return <>
        <form onSubmit={(e) => {formSubmit(e)}}>
            <label>Company Name</label>
            <input type="text" name="cname"/> <br/>

            <label>Company Email</label>
            <input type="text" name="cemail"/> <br/>

            <label>Company Address</label>
            <input type="text" name="caddres"/> <br/>
            <input type="submit" value="Save"/>
        </form>
    </>;

}
const element = <Test/>

ReactDOM.render(element, document.getElementById('root'));
```
