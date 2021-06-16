# useRef দিয়ে ref বানানো ও পাস করা

প্রথমেই useRef ইমপোর্ট করে আনতে হবে।

```javascript
import react, {useref} from 'react'
```

তারপর useRef\(\) হুকটাকে কল করতে হবে কম্পোনেন্টের মধ্যে। এটাতে একটা ইনিশিয়াল ভ্যালু দেয়া যেতে পারে, না দিলেও ক্ষতি নাই।

```javascript
const App = () => {
    //states......
    //............
    
    const blogFormRef = useRef()

}
```

তাহলেই রেফারেন্স তৈরি হয়ে গেলো। এবার ডমের এলিমেন্টটা বা ক্লাস কম্পোনেন্টকে এটা পাস করা যাবে।

```javascript
const App = () => {
    //states......
    //............
    
    const blogFormRef = useRef()
    
    return(
        <div>
        <p>Hello</p>
        <BlogForm ref={blogFormRef} />
    
    )
}
```

BlogForm যদি ক্লাস কম্পোনেন্ট হয় তাইলে সেটা এভাবেই পাস হয়ে যাবে। তবে ফাংশন কম্পোনেন্ট হলে এটিতে কাজ হবে না। তখন কাজে লাগাতে হবে forwardRef\(\) যেটা কি বা ref নিয়ে সেটা কম্পোনেন্ট ফাংশনকে পাস করবে। 

## 

