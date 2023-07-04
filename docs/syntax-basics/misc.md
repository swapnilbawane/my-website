---
sidebar_position: 5
---

# Misc tips

### 1. UUID

**Official site**
`https://www.npmjs.com/package/uuid`

- Install:
  `npm install uuid`

- Create a UUID (ES6 module syntax):

```javascript
import { v4 as uuidv4 } from "uuid";
const id = uuidv4();
```

---

### 2. Bootstrap Icons

Official resource - [Bootstrap Icons](https://icons.getbootstrap.com/)

```javascript title="App.css"
@import url("https://cdn.jsdelivr.net/npm/bootstrap-icons@1.10.5/font/bootstrap-icons.css");

// for home
 <i className="bi bi-house"> </i>

 // for explore
 <i className="bi bi-rocket"> </i>

 // for bookmark
 <i className="bi bi-bookmark"> </i>

 // for profile
 <i className="bi bi-person"> </i>

```

---

### 3. Google Fonts and Icons

```javascript title="App.css"
i.material-symbols-outlined {
    font-variation-settings:
    'FILL' 0,
    'wght' 400,
    'GRAD' 0,
    'opsz' 48;
    color: red;
    cursor: pointer;
  }

  i#red-fill.material-symbols-outlined {
    font-variation-settings:
    'FILL' 1,
    'wght' 400,
    'GRAD' 0,
    'opsz' 48;
    color: red;
    cursor: pointer;
}
```

```javascript title="index.html"
<head>
  <link
    rel="stylesheet"
    href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200"
  />
</head>
```

```javascript title="App.jsx"
 <div className="card-badge">
            <i
              className="material-symbols-outlined"
              onClick={() =>deleteRecipe(id)}
            >
              delete
            </i>
            <i
              className="material-symbols-outlined"
              id="red-fill"
              onClick={() => console.log("here")}
            >
              delete
            </i>
</div>
```

-------

### 4. Component for card

```javascript title="CardImageComponent.jsx"
<>
  <div className="card-cont">
    <div className="card-img">
      <div className="card-badge">
        <i
          className="material-symbols-outlined"
          onClick={() => console.log("here")}
        >
          favorite
        </i>
        <i
          className="material-symbols-outlined"
          id="red-fill"
          onClick={() => console.log("here")}
        >
          favorite
        </i>
      </div>

      <img src={image} alt="testimg" />
    </div>

    <div className="card-details">
      <div>
        {" "}
        <Link to={`/product/` + 1}> One </Link>{" "}
      </div>
      <b> Rs.10 </b>
      <b> Ratings: 4/5 </b>
    </div>

    <button
      className="card-button active-button"
      onClick={() => console.log("here")}
    >
      {" "}
      Add to Cart
    </button>
    <button
      className="card-button active-button"
      onClick={() => console.log("here")}
    >
      {" "}
      Go to Cart
    </button>
  </div>
</>
````

```javascript title="App.css"

.card-img, .card-cont, .card-badge, .card-details {
    display: flex;
    align-items: center;
}

.card-cont, .card-details {
    flex-direction: column;
    width: 240px;
    height: 451px;
}

.card-cont {
    background-color: rgb(246, 187, 187);
}

.card-img {
    justify-content: center;
    /* #8818081c */
    background: #8818081c;
    width: 13rem;
    height: 15rem;
    position: relative;
    padding: 2rem 1rem;
}

.card-img img {
    height: 90%;
    width: auto;
}

.card-badge .red-fav {
    color: red;
}

i.material-symbols-outlined {
    font-variation-settings:
    'FILL' 0,
    'wght' 400,
    'GRAD' 0,
    'opsz' 48;
    color: red;
    cursor: pointer;
  }

  i#red-fill.material-symbols-outlined {
    font-variation-settings:
    'FILL' 1,
    'wght' 400,
    'GRAD' 0,
    'opsz' 48;
    color: red;
    cursor: pointer;
}

.active-button {
    background-color: #3b82f6;
    cursor: pointer;
}

.card-button {
    color: #fff;
    text-align: center;
    padding: .5rem;
    width: 100%;
    border: none;
    font-family: Poppins;
    font-style: normal;
    font-weight: 600;
    background-color: #881808bf;
    cursor: pointer;
}


```
