# Example - 1

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
