---
sidebar_position: 3
---

# Common inputs

## 1. `Text`

```javascript
<label htmlFor="first-name">
First name:
 <input
 type="text"
 id="first-name"
 name="firstName"
 className=""
 style={{}}
 placeholder="placeholder text"
 value={}
 onChange={}
 ariaLabel="Enter your first name"
 minlength="4"
 maxlength="8"
 size="10"
 required
  />
```

## 2. `Number`
```javascript
<label htmlFor="tentacles">Number of tentacles (10-100):</label>

<input 
type="number" 
id="tentacles" 
name="tentacles"
min="10" 
max="100" />
```

## 3. `Email`

```javascript
<label
htmlFor="email">
Enter your globex.com email:
</label>

<input
type="email"
id="email"
pattern=".+@globex\.com"
size="30" required />
```



## 4. `Password`

Note: `htmlFor` and `name` attribute should be same for it to be linked

```javascript
<label htmlFor="password">
Repeat:
<input
type="password"
id="password"
name="password"
className=""
style={{}}
placeholder="placeholder text"
value={}
onChange={}
ariaLabel="Enter password"
/>
```

## 5. `Tel`
```javascript

<label htmlFor="phone">Enter your phone number:</label>

<input 
type="tel" 
id="phone" 
name="phone"
pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}"
required>

<small>Format: 123-456-7890</small>
```

## 6. `URL`
```javascript
<label htmlFor="url">Enter an https:// URL:</label>

<input 
type="url" 
name="url" 
id="url"
placeholder="https://example.com"
pattern="https://.*" 
size="30"
required />
```
------------

## 7. `Button`

```javascript
<button className="" onClick={() => functionName(arguments)}>
  Add to Archive
</button>
```

------------

## 8. `Radio`
```javascript
<fieldset>
    <legend>Select a maintenance drone:</legend>

    <div>
      <input type="radio" id="huey" name="drone" value="huey"
             checked />
      <label htmlFor="huey">Huey</label>
    </div>

    <div>
      <input type="radio" id="dewey" name="drone" value="dewey" />
      <label htmlFor="dewey">Dewey</label>
    </div>

    <div>
      <input type="radio" id="louie" name="drone" value="louie" />
      <label htmlFor="louie">Louie</label>
    </div>
</fieldset>
```

## 9. `Dropdown`

```javascript
<label htmlFor="repeat">
  Repeat:
  <select name="repeat" id="repeat" onChange={habitHandler}>
    <option> Select </option>
    <option value="daily">Daily</option>
    <option value="monthly">Monthly</option>
    <option value="weekly">Weekly</option>
  </select>
</label>
```

## 10. `Checkbox`

```javascript
<fieldset>
    <legend>Choose your monster's features:</legend>

    <div>
      <input
      type="checkbox"
      id="scales"
      name="scales"
      checked />
      <label htmlFor="scales">Scales</label>
    </div>

    <div>
      <input
      type="checkbox"
      id="horns"
      name="horns" />
      <label htmlFor="horns">Horns</label>
    </div>

</fieldset>
```
------------

## 11. `Search`
```javascript

<label htmlFor="site-search">Search the site:</label>
<input type="search" id="site-search" name="q" />

<button>Search</button>
```

------------
## 12. `File`
```javascript
<label 
htmlFor="avatar">
Choose a profile picture:
</label>

<input 
type="file"
id="avatar"
name="avatar"
accept="image/png, image/jpeg" 
/>
```
## 13. `Color`
```javascript
<p>Choose your monster's colors:</p>

<div>
    <input 
    type="color" 
    id="head" 
    name="head"
    value="#e66465" />
    <label htmlFor="head">Head</label>
</div>

<div>
    <input 
    type="color" 
    id="body" 
    name="body"
    value="#f6b73c" />
    <label htmlFor="body">Body</label>
</div>

```

## 14. `Range`
```javascript
<p>Audio settings:</p>

<div>
  <input type="range" id="volume" name="volume"
         min="0" max="11" />
  <label htmlFor="volume">Volume</label>
</div>

<div>
  <input type="range" id="cowbell" name="cowbell" 
         min="0" max="100" value="90" step="10" />
  <label htmlFor="cowbell">Cowbell</label>
</div>


```
## 15. `Image`
```javascript
<p>Sign in to your account:</p>

<div>
  <label htmlFor="userId">User ID</label>
  <input 
  type="text" 
  id="userId" 
  name="userId" />
</div>

<input 
type="image" 
id="image" 
alt="Login"
src="/media/examples/login-button.png" />

```









