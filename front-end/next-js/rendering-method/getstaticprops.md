# স্ট্যাটিক জেনারেশন \(getStaticProps\)

### getStaticProps

এটা বিল্ড টাইমে ডেটা ফেচ করে, সেটা ইন্টার্নাল বা এক্সটার্নাল সোর্স থেকে হতে পারে তবে অবশ্যই ডেটা স্ট্যাটিক হতে হবে।



প্রথমে যে কম্পোনেন্টে ডেটা ফেচ করবো সেখানে geStaticProps ফাংশনটাকে async ফাংশন হিসেবে এড করে এক্সপোর্ট করতে হবে।

```javascript
export async function getStaticProps()
{
  const allData = getPostSorted()
  return {
    props: {
      allData
    }
  }
}
```

এখানে একটা অবজেক্ট রিটার্ন করা হচ্ছে যেটাতে props অবজেক্টের মদ্যে ভ্যালুটা আছে।

তারপর যে নামে props-এ ডেটা আছে সে নামেই কম্পোনেন্টে props হিসেবে তা এক্সপোর্ট করে আনবো।

```javascript
export default function Home({allData})
```





