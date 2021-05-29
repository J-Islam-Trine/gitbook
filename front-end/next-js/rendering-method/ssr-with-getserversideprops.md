# সার্ভার সাইড রেন্ডারিং \(SSR with getServerSideprops\)

getServerSideProps\(\) অনেকাংশেই getStaticProps\(\)-এর মতনই।

```javascript
export async function getServerSideProps(context) {
  return {
    props: {
      // props for your component
    }
  }
}
```

এখানে context একটা অবজেক্ট যেটা রিকুয়েস্ট, রেসপন্স, লোকালের মতন নানান প্যারামিটার স্টোর করে। এটা ব্যবহার করতে হয় না।

