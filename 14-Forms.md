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



Formik Demo
```
import React, { Component } from 'react';
import ReactDOM from 'react-dom';
import { Formik } from 'formik';

const Basic = () => (
    <div>
      <h1>Anywhere in your app!</h1>
      <Formik
        initialValues={{ email: '', password: '' }}
        validate={values => {
          const errors = {};
          if (!values.email) {
            errors.email = 'Required';
          } else if (
            !/^[A-Z0-9._%+-]+@[A-Z0-9.-]+\.[A-Z]{2,}$/i.test(values.email)
          ) {
            errors.email = 'Invalid email address';
          }
          return errors;
        }}
        onSubmit={(values, { setSubmitting }) => {
          setTimeout(() => {
            alert(JSON.stringify(values, null, 2));
            setSubmitting(false);
          }, 400);
        }}
      >
        {({
          values,
          errors,
          touched,
          handleChange,
          handleBlur,
          handleSubmit,
          isSubmitting,
          /* and other goodies */
        }) => (
          <form onSubmit={handleSubmit}>
            <input
              type="email"
              name="email"
              onChange={handleChange}
              onBlur={handleBlur}
              value={values.email}
            />
            {errors.email && touched.email && errors.email}
            <br/>
            <input
              type="password"
              name="password"
              onChange={handleChange}
              onBlur={handleBlur}
              value={values.password}
            />
            {errors.password && touched.password && errors.password}
            <br/>
            <button type="submit" disabled={isSubmitting}>
              Submit
            </button>
          </form>
        )}
      </Formik>
    </div>
  );
const element = <Basic/>

ReactDOM.render(element, document.getElementById('root'));
```
