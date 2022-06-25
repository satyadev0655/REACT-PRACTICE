Ex-1

```
import React, { useState, useEffect } from 'react';
import ReactDOM from 'react-dom';

function Example() {
  const [companies, setCompanies] = useState([]);

 useEffect(()=>{
    fetch('http://app1.dev-app.cf/api/v1/companies')
    .then((res) => res.json())
    .then((result) => {
      setCompanies(result.data);
    });
 })

   return (
      <div>
        <h2>Companies Data...</h2>
        <table>
          <thead>
            <tr>
              <th>Id</th>
              <th>Name</th>
              <th>Email</th>
              <th>Location</th>
            </tr>
          </thead>
          <tbody>
            {companies.map((company) => (
              <tr key={company.id}>
                <td>{company.id}</td>
                <td>{company.name}</td>
                <td>{company.email}</td>
                <td>{company.address}</td>
              </tr>
            ))}
          </tbody>
        </table>
      </div>
    );
  }
const element = <Example/>

ReactDOM.render(element, document.getElementById('root'));
```
