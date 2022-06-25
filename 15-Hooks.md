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
