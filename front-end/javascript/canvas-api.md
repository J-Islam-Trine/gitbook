# ক্যানভাস এপিআই\(Canvas API\)

### পেজে ক্যানভাস এড করা

```markup
<canvas id="canvas"></canvas>
```

### ক্যানভাস সিলেক্ট করা

এবারে স্ক্রিপ্টে আমরা ক্যানভাসটাকে সিলেক্ট করি -

```text
const canvas =  document.getElementById('#canvas');
```

### রেন্ডারিং কনটেক্সট অ্যাকসেস করা

```text
const canvasContext = canvas.getContext('2d');
```

### ক্যানভাসের দৈর্ঘ্য প্রস্থ সেট করা

ক্যানভাসের দৈর্ঘ্য আর প্রস্থটা চাইলে এইচটিএমএল পেজে সেট করে নিতে পারতাম, তবে তার বদলে স্ক্রিপ্টে সেট করাটাই সুবিধাজনক মনে হইছে আমার। আবার তারচেয়ে ভালো হয় সিএসএস রুলসে এড করে নিলে।

```text
canvas.width = 400;
canvas.height = 400;
```

### ক্যানভাসের জন্য পেইজে ইমেজ অ্যাড করা

```text
<img src="https://i.ibb.co/HHBFJdH/char.png" id="character" alt="">
```

### ইমেজ হাইড করা

```css
#charcater
{
display: none;
}
```

### ক্যানভাস কো-অর্ডিনেট

![](../../.gitbook/assets/image%20%281%29.png)

### ক্যানভাসে ইমেজ ড্র করা

```javascript
canvasContext.drawImage(charImage, 10, canvas.height-30,25,20);
```

### পড়া যেতে পারে

{% embed url="https://developer.mozilla.org/en-US/docs/Web/API/Canvas\_API/Tutorial" %}

