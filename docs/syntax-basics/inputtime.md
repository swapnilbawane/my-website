---
sidebar_position: 8
---

# Time inputs

## 1. `Time`
```javascript
<label 
htmlFor="appt">
Choose a time for your meeting:
</label>

<input 
type="time" 
id="appt" 
name="appt"
min="09:00" 
max="18:00" 
required />

<small>Office hours are 9am to 6pm</small>
```


## 2. `Date`

```javascript
<label htmlFor="start">
Start date:
</label>

<input 
type="date" 
id="start" 
name="trip-start"
value="2018-07-22"
min="2018-01-01" 
max="2018-12-31" 
/>

```


## 3. `Date-Time Local`
```javascript
<label htmlFor="meeting-time">
Choose a time for your appointment:
</label>

<input 
type="datetime-local" 
id="meeting-time"
name="meeting-time" 
value="2018-06-12T19:30"
min="2018-06-07T00:00" 
max="2018-06-14T00:00" 
/>

```

## 4. `Week`
```javascript

<label htmlFor="week">
Choose a week in May or June:
</label>

<input 
type="week" 
name="week" 
id="camp-week"
min="2018-W18" 
max="2018-W26" 
required />

```
