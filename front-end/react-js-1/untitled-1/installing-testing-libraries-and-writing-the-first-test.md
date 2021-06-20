# টেস্টিং লাইব্রেরি ইনস্টল করা ও টেস্ট লেখা \(Installing testing libraries and writing the first test\)

### ইনস্টলেশন

রিঅ্যাক্টে কম্পোনেন্ট টেস্ট করতে হলে নিচের লাইব্রেরিগুলো ইনস্টল করতে হবে।

```text
npm install --save-dev @testing-library/react @testing-library/jest-dom
```

এর একটা হচ্ছে React testing Library নামের একটা লাইব্রেরি আর অন্যটি হচ্ছে jest। 

### টেস্ট ফাইল ক্রিয়েট করা

এরপর কম্পোনেন্ট \(যেমন, home.jsx\)-এর ফোল্ডারে ঐ নামেই .test.js এক্সটেনশন দিয়ে\(home.test.js\) নামের একটা ফাইল বানাতে হবে।

### টেস্ট লেখা

প্রথমে নিচের কম্পোনেন্টগুলা ইমপোর্ট করে আনি

```javascript
import React from 'react'
import '@testing-library/jest-dom/extend-expect'
import { render } from '@testing-library/react'
```

এবার যে কম্পোনেন্টের জন্য টেস্ট সেটাকে ইমপোর্ট করে আনি।

```javascript
import Quest from './singleQuest'
```

এবারে test লেখা যাবে নিচের মত করে

```javascript
test('tast name', () => {
//test content
//...
//...
})
```

এবারে টেস্টের ভেতরে কম্পোনেন্ট রেন্ডার করবো নিচের মত করে - 

```javascript
test('tast name', () => {
    const newQuest = {
    title: "some title,
    detail: "some text}
    const component = render(<Quest quest={newQuest} />)
})
```

তারপর আমরা সেটার কন্টেন্ট চেক করতে পারি।

```javascript
test('tast name', () => {
    const component = render(<Quest quest={newQuest} />)
    expect(component.container).toHaveTextContent('some text')
})
```

### টেস্ট রান করা

CRA-তে jest কনফিগ করা থাকে বলে **npm run test** দিয়েই টেস্ট রান করানো যাবে। তবে এক্ষেত্রে টেস্ট ওয়াচ মোডে রান হবে অর্থাৎ টেস্ট যতবার সেভ হবে তত বার তা রান হবে।

