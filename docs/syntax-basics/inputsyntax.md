---
sidebar_position: 3
---

# Common inputs 

1. `input type="text`
```javascript
<label htmlFor="first-name">
First name:
 <input 
 type="text" 
 className="" 
 id="first-name"
 name="firstName"
 value={}
 onChange={}
  />
```

2. `input type="password`
```javascript
<label htmlFor="password">
Repeat:
<input 
type="password" 
className="" 
id="password" 
/>
```

3. `select - dropdown`
```javascript
<label htmlFor="repeat">
Repeat:
 <select 
 name="repeat" 
 id="repeat"
 onChange={habitHandler}
 >
       <option> Select </option>
       <option value="daily">Daily</option>
       <option value="monthly">Monthly</option>
       <option value="weekly">Weekly</option>
</select>
</label>
```

4. `Button`
```javascript
<button 
className=""
onClick={() => functionName(arguments)}
>
Add to Archive
</button>
```

