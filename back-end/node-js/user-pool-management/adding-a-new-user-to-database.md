# পাসওয়ার্ড হ্যাশ জেনারেট করা \(Generating Password Hash\)

* bcrypt ইনস্টল করি।

```text
npm install --save bcrypt
```

* bcrypt ইমপোর্ট করি

```javascript
const bcrypt = require('bcrypt')
```

* পাসওয়ার্ডের হ্যাশ জেনারেট করি।

```javascript
const saltRounds = 10;
const passwordHash = await bcrypt.hash(userSubmittedPassword, saltRounds)
```

* json রেসপন্স-এর transform ফাংশনটা আপডেট করি \(model-এ\), যাতে করে পাসওয়ার্ড হ্যাশ রেসপন্সের সাথে না আসে।

```javascript
userSchema.set('toJSON', {
    transform: (doc, ret) => {
        //ret.id = ret._id.toString();
        //delete ret._id;
       // delete ret.__v;
        delete ret.passwordHash;
    }
})
```

#### রেফারেন্স

{% page-ref page="../../../snippets/undefined.md" %}



