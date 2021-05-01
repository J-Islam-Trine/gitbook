# অথেনটিকেশন হেডার থেকে টোকেন নেয়া আর ভেরিফাই করা

```javascript
const getToken = req => {
    const auth = req.get('authorization')
    if(auth && auth.toLowerCase().startsWith('bearer '))
    {
        return auth.substring(7)
    }
    else return null
}

//inside route
const token = getToken(req);
const decodedToken = jwt.verify(token, process.env.secret)
```



