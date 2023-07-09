---
sidebar_position: 14
---

# Styled Buttons

```javascript title="Buttons.jsx"
<div className="classic-buttons">
  <button className="button">Add to Archive</button>

  <button className="active-button">Remove Archive</button>
</div>
```

```javascript title="Buttons.css"
.classic-buttons {
  display: flex;
  gap: 10px;
  justify-content: center;
  width: 17rem;
}

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
```
