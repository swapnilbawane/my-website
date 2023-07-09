---
sidebar_position: 13
---

# Styled Card 

## This contains a styled card with notification type Google icons. 

```javascript title="index.html"
<head>
  <link
    rel="stylesheet"
    href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200"
  />
</head>
```

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

```javascript title="StyledComponent.jsx"
 <>
        <div className="card-cont">
          <div className="card-img">
            <img
              src="https://b.zmtcdn.com/data/dish_photos/9e7/bdf4fa911a76e5ba0656f5adad9749e7.png?output-format=webp"
              alt="testimg"
            />

            <div className="card-badge">
              <i
                className="material-symbols-outlined"
                onClick={() => console.log('here')}
              >
                favorite
              </i>

              <i
                className="material-symbols-outlined"
                // id="red-fill"
                onClick={() => console.log('here')}
              >
                delete
              </i>
            </div>
          </div>

          <div className="card-details">
            <div>
              {' '}
              <Link to="https://www.google.com"> One </Link>{' '}
            </div>
            <b> Rs.10 </b>
            <b> Ratings: 4/5 </b>
          </div>

          <div className="button-container">
            <button className="card-button" onClick={() => console.log('here')}>
              Add to Cart
            </button>
            <button
              className="card-button active-button"
              onClick={() => console.log('here')}
            >
              Go to Cart
            </button>
          </div>
        </div>
      </>
```

```javascript title="Card.css"
.card-cont {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 17rem;
  height: 340px;
  background-color: rgb(246, 187, 187);
  gap: 10px;
}

/*  IMAGE */

.card-img {
  display: flex;
  /* flex-direction: column; */
  align-items: flex-start;
  justify-content: center;
  /* background: #cd441649; */
  width: 12rem;
  height: 8rem;
  position: relative;
  padding: 1.5rem 2rem 0rem 3rem;
  gap: 10px;
}

.card-img img {
  height: 100%;
  width: auto;
}

/*  BADGE DETAILS */
.card-badge {
  display: flex;
  align-items: center;
  margin-left: -25px;
  margin-top: -15px;
}

.card-badge .red-fav {
  color: red;
}

i.material-symbols-outlined {
  font-variation-settings: 'FILL' 0, 'wght' 400, 'GRAD' 0, 'opsz' 48;
  color: red;
  cursor: pointer;
}

i#red-fill.material-symbols-outlined {
  font-variation-settings: 'FILL' 1, 'wght' 400, 'GRAD' 0, 'opsz' 48;
  color: red;
  cursor: pointer;
}

/* CARD CONTAINER */

.card-details {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 240px;
}

/* BUTTONS */
.button {
  color: white;
  background-color: blue;
  cursor: pointer;
}

.active-button {
  color: white;
  background-color: black;
  /* background-color: #3b82f6; */
  cursor: pointer;
}

.button-container {
  display: flex;
  flex-direction: column;
  gap: 10px;
}


.card-button {
  color: #fff;
  text-align: center;
  padding: 0.5rem;
  width: 10rem;
  border: none;
  font-family: Poppins;
  font-style: normal;
  font-weight: 600;
  background-color: #881808bf;
  cursor: pointer;
}
```