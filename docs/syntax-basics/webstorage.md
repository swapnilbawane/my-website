---
sidebar_position: 16
---

# Local Storage Basics

**Live Link:**  https://stackblitz.com/edit/stackblitz-starters-o7xcyl?file=src%2FLocal.jsx

```javascript title="LocalStorage.jsx"

import React, { useState } from 'react';

export function Local() {
  const saveLocal = () => {
    const sampleObject = [
      {
        number: '123',
      },
      {
        number: '123',
      },
    ];

    const sampleObject2 = { number: '123' };

    localStorage.setItem('home', 'home123');
    localStorage.setItem('sampleObject', JSON.stringify(sampleObject));
  };

  const showLocal = () => {
    const homeValue = localStorage.getItem('home');
    const sampleValue = localStorage.getItem('sampleObject');
    const parsedValue = JSON.parse(sampleValue);
    setSample(parsedValue);
    console.log({ homeValue });
    console.log({ parsedValue });
  };

  const [sample, setSample] = useState([]);

  return (
    <>
      <button onClick={() => saveLocal()}>Save to Local Storage</button>

      <button onClick={() => showLocal()}>Get from local storage</button>

      {sample.map((item, index) => {
        return <div key={index}>{item?.number}</div>;
      })}
    </>
  );
}


```

```javascript title="LocalStorageGeneral.jsx"

- Adds a data item to it using `Storage.setItem()`

`localStorage.setItem("myCat", "Tom");`


- The syntax for reading the localStorage item is as follows:

`const cat = localStorage.getItem("myCat");`

- The syntax for removing the localStorage item is as follows:

`localStorage.removeItem("myCat");`

-The syntax for removing all the localStorage items is as follows:

`localStorage.clear();`

-------

```