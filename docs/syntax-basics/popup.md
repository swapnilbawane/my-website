---
sidebar_position: 4
---

# Popup - React Popup lib

**Get started here** - [React-Popup installation instructions](https://react-popup.elazizi.com/getting-started/)

```
npm install reactjs-popup --save
```

```javascript
import Popup from "reactjs-popup";
import "reactjs-popup/dist/index.css";

export function Habits() {
  return (
    <Popup
      trigger={<button className="button"> Show Details </button>}
      modal
      nested
    >
      {(close) => (
        <div className="modal">
          <button className="close" onClick={close}>
            &times;
          </button>

          <div className="header"> Add your Habit </div>

          <div className="content">
            {/* Habit Title  */}
            <div className="habit-title">
              <label htmlFor="habit-name">
                Name:
                <input
                  type="text"
                  name="habit-name"
                  value={item.name}
                  className="habit-name-field"
                  onChange={habitHandler}
                  contentEditable="true"
                />
              </label>
            </div>
          </div>

          <div className="actions">
            <button
              className="button"
              onClick={() => {
                console.log("details saved ");
                close();
              }}
            >
              Edit and Save Details
            </button>
          </div>
        </div>
      )}
    </Popup>
  );
}
```
