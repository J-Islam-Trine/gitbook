# সাইড ইফেক্ট হুক \(useEffect\)

### ইউসেজ

কম্পোনেন্ট রেন্ডার করার পর দিয়েই কিছু করতে হলে সেটার জন্য এইটা ব্যবহার করা হয়।

* ম্যানুয়ালি ডম ম্যানিপুলেট করা,
* বাইরের ডেটা ফেচ করা

### কীভাবে?

প্রথমেই useEffect ইমপোর্ট করতে হবে।

```javascript
import {useEffect} from 'react'
```

এরপর যে ফাংশনের ইফেক্ট, সেটার মধ্যে তা ব্যবহার করা যাবে।

```javascript
 const SomeComponent = () => {
   useEffect(()=> {

//....
//...

})
 
 return(
 //...
 //...
 )
 }
```

**উপরের এক্সাম্পলে থাকা useEffect হুকটা প্রতি বার রেন্ডারিং-এই রান করবে।** 

### কিছু পয়েন্ট

* useEffect লুপের মধ্যে দেয়া যাবে না। 
* useEffect কন্ডিশন দিয়ে রান করা যাবে না।
* useEffect-এর মধ্যে যে ফাংশন পাস করা হচ্ছে সেইটা async হতে পারবে না।অর্থাৎ নিচের মত হতে পারবে না - 

```javascript
useEffect( async ()=> {

//....
//...

})
```

### useEffect-এর মধ্যে async/await ব্যবহার করা

```javascript
  useEffect(() => {
   async  function apiCaller()
    {
      //do some async/await action here.......
    )  
    apiCaller()
  }, [user])
```

### শুধু মাত্র একবার useEffect রান করা

```javascript
useEffect(()=> {

//....
//...

}, [])
```

useEffect দ্বিতীয়া আরেকটা আর্গুমেন্ট দেয়, যেটা একটা অ্যারে। এটা খালি রেখে দিলে useEffect শুধু মাত্র কম্পোনেন্ট প্রথম বার মাউন্ট হওয়ার পরই রান করবে।



### useEffect স্কিপ করা

useEffect চাইলে কোন স্টেট-এর ভ্যালুর ভিত্তিতে রান করা যায়। এতে কী হয়, ওটা শুধু এক বারও রান করে না আবার প্রতি রেন্ডারে রান করতেও থাকে না। শুধু স্টেট আপডেট হলে তখনই রান করে।

```javascript
  useEffect(() => {
   blogService.getAll().then(blogs =>
      setBlogs( blogs )
    )  
  }, [user])
```

এই useEffect হুক user স্টেটের উপর নির্ভর করবে। সেটা বদলালে useEffect রান করবে।







