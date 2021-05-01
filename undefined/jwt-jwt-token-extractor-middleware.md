# JWT টোকেন এক্সট্রাক্টর মিডলওয়্যার \(JWT Token Extractor Middleware\)

```javascript
module.exports = {
    getToken: function(req, res, next) {
        const auth = req.get('authorization')
        let token = null;
        if(auth && auth.toLowerCase().startsWith('bearer '))
        {
            console.log(auth.substring(7))
            token = auth.substring(7)
        }
        req.token = token;
        next()
        
        
    }
}
```

