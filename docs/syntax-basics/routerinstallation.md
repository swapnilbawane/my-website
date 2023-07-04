---
sidebar_position: 1
---

# React Router

## Installation
`npm install react-router react-router-dom`

## index.js / main.js setup 
```javascript title="index.js"

import { BrowserRouter } from "react-router-dom";


ReactDOM.createRoot(document.getElementById("root")).render(
  <React.StrictMode>
    <BrowserRouter>
    
        
          <App />
     
   
    </BrowserRouter>
  </React.StrictMode>
);

```

-----------

## Sample Component to render at / 
```javascript title="Home.jsx"
export function Home() { 
    return(
        <>
        Home Page 
        </>
    );
}
```

## App.jsx setup for Routing 
```javascript title="App.jsx"

import { Routes, Route } from "react-router-dom";

export function App() { 

return(
  <>
      <Routes>
        <Route path="/" element={<Home />} />
      </Routes>
    </>

);
}
```