# ফাংশনাল কম্পোনেন্টে ref \(Handling ref in functional component\)

যে ফাংশনে ref পাঠানো হচ্ছে সেটা যাতে refটাতে অ্যাকসেস করতে পারে, সেটার জন্য আমাদেরকে দুইটা কাজ করতে হবে - 

* যদি React ইমপোর্ট না করা থাকে তাহলে তা ইমপোর্ট করতে হবে।

```javascript
import React from 'react'
```

* এরপর যে কম্পোনেন্টটা ref-এ অ্যাকসেস করবে সেটাকে forwardRef-এর একটা প্যারামিটার হিসেবে পাস করতে হবে। যেমন নিচের কম্পোনেন্ট - 

```javascript
const Greeting = () => {
    
    return(
    <div>
    <p>Hello!</p>
    </div>
    )

}
```

হয়ে যাবে নিচের মত - 

```javascript
const Greeting = React.forwardRef((props. ref =>{
        return(
    <div>
    <p>Hello!</p>
    </div>
    )

})
```

এবারে চাইলে আমরা নির্দিষ্ট কোন এলিমেন্টে তা এটাচ করতে পারি।

```javascript
const Greeting = React.forwardRef((props. ref =>{
        return(
    <div>
    <p>Hello!</p>
    <button ref={ref}>Click me</button>
    </div>
    )

})
```

অথবা এই কম্পোনেন্টের যে কোন ফাংশনকে এক্সপোজ করা যাবে useImperativeHandle হুক দিয়ে।

