---
sidebar_position: 6
---

# Context Setup

```javascript title="src/Context/data-context.jsx"
import { useContext, createContext } from "react";
import { useState } from "react";

export const DataContext = createContext();

export function DataProvider({ children }) {
 
 const initialHabitDetailsState = {
    name: "",
    repeat: "",
    goal: "",
    timeofDay: "",
    startDate: "",
  };

  const [habit, setHabit] = useState(initialHabitDetailsState);

  const habitHandler = (event) => {
  };

  return (
    <DataContext.Provider
      value={{ habit, setHabit, habitHandler, initialHabitDetailsState }}
    >
      {children}
    </DataContext.Provider>
  );
}

export const useData = () => useContext(DataContext);
```

----------

```javascript title="src/index.js"

import React from "react";
import ReactDOM from "react-dom/client";
import App from "./App.jsx";
import "./index.css";
import { BrowserRouter } from "react-router-dom";
import { DataProvider } from "src/Context/data-context.jsx";


ReactDOM.createRoot(document.getElementById("root")).render(
  <React.StrictMode>
    <BrowserRouter>
    
      <DataProvider>
        
          <App />
     
      </DataProvider>
      
    </BrowserRouter>
  </React.StrictMode>
);
```

----------

```javascript title="src/Pages/Home.jsx"

import { useData } from "src/Context/data-context.js" 

export function Home() { 
    // code
}

```