# কম্পোনেন্ট লেভেল স্টাইলিং \(Component Level Styling\)

## Styled JSX

Next.js Styled-JSX ডিফল্ট ভাবেই সমর্থন করে থাকে। 

### ইনস্টলেশন

```text
npm install --save styled-jsx
```

### ইউসেজ

babel-এর প্লাগইন হিসেবে ইউজড হয় বলে Styled JSX ইমপোর্ট করতে হয় না।

### উদাহরণ

```javascript
export default function App() {
  return (
    <div>
      //...
      //...
      <style jsx>{`
        //...
        //...
      `}</style>
    </div>
  );
}
```

## CSS মডিউল

CSS মডিউল হচ্ছে কম্পোনেন্ট লেভেল স্কোপ সহ CSS ফাইল। React বা Next.js এটাকে বাই ডিফল্ট সমর্থন করে।

### ইনস্টলেশন

নেই।

### ইউসেজ

css module ব্যবহার করে স্টাইল করতে গেলে শুধু মাত্র class ব্যবহার করে স্টাইল করতে হবে।

* কম্পোনেন্টের জন্য module.css এক্সটেনশন দিয়ে একটি ফাইল তৈরি করি।
* তারপর সেটাতে শুধু মাত্র class ব্যবহার করে স্টাইল লিখি।
* এবারে সেই ফাইলটাকে কম্পোনেন্টে এক্সপোর্ট করে আনি আর className দিয়ে স্টাইল করি।

```javascript
import styles from './App.module.css'
export default function App() {
  return (
    <div>
    <p className={styles.title}>Headline</p>
    </div>
  );
}
```







