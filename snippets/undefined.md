# পাসওয়ার্ড হ্যাশ জেনারেট করা ও লগইন ডিটেইলস স্টোর করা



```javascript
const bcrypt = require('bcrypt')

const saltRounds = 10;
        const passwordHash = await bcrypt.hash(request.body.password, saltRounds)
    
        const newUser = new User({
            username: request.body.username,
            passwordHash: passwordHash
        })
    
        const dbResponse = await newUser.save();
```

