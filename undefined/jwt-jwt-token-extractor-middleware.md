# JWT টোকেন আর ইউজার আইডি এক্সট্রাক্টর  মিডলওয়্যার \(JWT Token & User ID Extractor Middlewares\)



```javascript
const jwt = require('jsonwebtoken')

module.exports = {
    getToken: function(req, res, next) 
    {
        const auth = req.get('authorization')
        let token = null;
        if(auth && auth.toLowerCase().startsWith('Bearer '))
        {
            // console.log(auth.substring(7))
            token = auth.substring(7)
        }
        req.token = token;
        next()    
    },
    userExtractor: function (request, response, next)
    {
        let decodedToken;
        if (request.token == null)
        {
            request.user = null
        }
        else
        {
             decodedToken = jwt.verify(request.token, process.env.secret)

        if (!decodedToken.id)
        {
            request.user =  null
        }
        else 
        {
            
         request.user =  decodedToken.id
        }
    }
        next()
    }
}
```

