# Example - 1 &&

```
import React from 'react';
import './style.css';

export default function App() {
  // const users = [
  //   { id: 1, name: 'Alex' },
  //   { id: 2, name: 'Benn' },
  // ];

  const users = [];

  return <div>
    
    {
    users.length > 0 && users.map((user) => user.name)
    
    }

  {
    users.length == 0 && <p>No User Records found</p>
    
    }
    
    </div>;
}

```

Output
No User Records found


# Example -2 Ternary
```
import React from 'react';
import './style.css';

export default function App() {
  const users = [
    { id: 1, name: 'Alex' },
    { id: 2, name: 'Benn' },
  ];

  // Ternary a > b ? "a is big" : "b is big"

  //const users = [];

  return (
    <div>
      {users.length > 0 ? (
        users.map((user) => user.name)
      ) : (
        <p>No User Records found</p>
      )}
    </div>
  );
}
```
