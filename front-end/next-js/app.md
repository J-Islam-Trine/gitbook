# অ্যাপ \(App\)

Next.js পেজগুলো ইনিশিয়ালাইজ করতে App কম্পোনেন্ট ব্যবহার করে থাকে। তবে কাস্টম App কম্পোনেন্টও ক্রিয়েট করা যাবে নিচের মত করে - 

pages ফোল্ডারে **\_app.js** নামে একটা ফাইল ক্রিয়েট করি।

তারপর তাতে নিচের কম্পোনেন্ট অ্যাড করি।

```javascript
function MyApp({ Component, pageProps }) {
  return <Component {...pageProps} />
}
```

