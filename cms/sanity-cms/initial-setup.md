# প্রারম্ভ \(Initial Setup & Booting Up\)

### Sanity গ্লোবাল ইনস্টলেশন

```text
npm install -g @sanity/cli
```



### Sanity প্রজেক্ট তৈরি

প্রজেক্টের জন্য একটা ফোল্ডার বানিয়ে সেখানে রান করতে হবে

```text
sanity init
```



{% hint style="danger" %}
### ইনস্টল করার সময় অবশ্য powershell ব্যবহার করতে হবে বা cmder। Bash cli-তে কিন্তু অপশান সিলেক্ট করা যায় না।
{% endhint %}

### ইনস্টলেশনের সময়

ইনস্টলেশনের সময় Sanity বেশ কিছু জিনিস দিতে বলবে, যেমন প্রজেক্টের নাম, ডিফল্ট ডেটাসেট কোনটা হবে সেটা, প্রজেক্টের আউটপুট কই হবে, কোন টেম্পলেট ইউজ করা হবে কি না ইত্যাদি। এটা আরো জানা যাবে এই লিংক থেকেঃ [https://www.sanity.io/docs/init](https://www.sanity.io/docs/init)

### শুরু করা

এবারে একই ফোল্ডারে 

```text
sanity start
```

কমান্ডটা রান করলে Sanity Studio চালু হয়ে যাবে। Sanity Studioটাই মূলতঃ আমাদের CMS-এর ইউজার ইন্টারফেস।

