---
sidebar_position: 10
---

# Auth syntax 

## Login 
```javascript title="Login.jsx"

const handleLogin = async (user) => {
        try {
            const creds = {
                username: user.username,
                password: user.password,
            }

            const res = await axios.post(
                '/api/auth/login',
                JSON.stringify(creds)
            )

            if (res.status === 200) {
                const { foundUser, encodedToken } = res.data

                localStorage.setItem('encodedToken', encodedToken)
                setLoggedIn(true)
                setLoggedUserName(user.username)
                navigate('/home')
                showLoggedInToastMessage()
            } else if (res.status === 404) {
                usernameNotFoundToastMessage()
            } else if (res.status === 401) {
                passwordWrongToastMessage()
            } else if (res.status === 500) {
                errorLoginToastMessage()
            }
        } catch (error) {
            console.log(error)
        }
    }
```

## Guest Login 

```javascript title="GuestLogin.jsx"
const handleGuestLogin = async () => {
        try {
            const creds = {
                username: 'adarshbalika',
                password: 'adarshBalika123',
            }

            const res = await axios.post(
                '/api/auth/login',
                JSON.stringify(creds)
            )

            if (res.status === 200) {
                const { foundUser, encodedToken } = res.data

                localStorage.setItem('encodedToken', encodedToken)
                setLoggedIn(true)
                setLoggedUserName('adarshbalika')
                navigate('/home')
                showLoggedInToastMessage()
            }
            else if (res.status === 404) {
                usernameNotFoundToastMessage()
            } else if (res.status === 401) {
                passwordWrongToastMessage()
            } else if (res.status === 500) {
                errorLoginToastMessage()
            }

        } catch (error) {
            console.log(error)
        }
    }
```

## Signup 
```javascript title="Signup.jsx"
const handleSignup = async (user) => {
        // console.log('received user', user)

        try {
            const creds = {
                firstName: user.firstName,
                lastName: user.lastName,
                username: user.username,
                password: user.password,
                profileimage:
                    'https://res.cloudinary.com/djhnar3ju/image/upload/v1688106576/Gravatar/Gravatar_2.jpg',
            }

            const res = await axios.post(
                '/api/auth/signup',
                JSON.stringify(creds)
            )

            if (res.status === 201) {
                const { createdUser, encodedToken } = res.data
                // console.log("createdUser", createdUser)
                localStorage.setItem('encodedToken', encodedToken)
                setLoggedIn(true)
                setLoggedUserName(user.username)
                navigate('/home')
                showLoggedInToastMessage()
            }
            else if (res.status === 422) {
                usernameExistsToastMessage()
            } else if (res.status === 500) {
                errorSignupToastMessage()
            }
        } catch (error) {
            console.log(error)
        }
    }
```

## Logout 
```javascript title="Logout.jsx"
const handleLogout = () => {
        localStorage.removeItem('encodedToken')
        setLoggedIn(false)
        loggedOutToastMessage()
        navigate('/')

    }
```


