---
sidebar_position: 11
---

# API Calls

## Fetch GET

```javascript
try { 
const response = await fetch('/api/posts')
}
catch(error) { 

}
```

## Fetch GET with header
```javascript
try { 
const response = await fetch('/api/users/bookmark/', {
                method: 'GET',
                headers: {
                    'Content-Type': 'application/json',
                    authorization: `${encodedToken}`,
                },
            })

if(response.status===200) { 

}           
}
catch(error) { 

}
```

## Fetch POST with header and body 
```javascript
 const response = await fetch(`/api/users/edit/`, {
                method: 'POST',
                body: JSON.stringify(sendUserData),
                headers: {
                    'Content-Type': 'application/json',
                    authorization: `${encodedToken}`,
                },
            })

if(response.status===200) { 

}           
```



## Axios GET with no body 
```javascript
try { 
const response = await axios.get('/api/users')

if(response.status===200) { 

}
}
catch(error) { 

}
```

## Axios POST with body 
```javascript

try {
const res = await axios.post(
                '/api/auth/login',
                JSON.stringify(creds)
            )
 if (res.status === 200) { 

 }
}
catch(error) {

}
```
