# prettyDOM দিয়ে একটা এলিমেন্টের আউটপুট দেখা\(Viewing the HTML output for a element with prettyDOM\)

চাইলে prettyDOM দিয়ে কোন একটা এলিমেন্টের আউটপুটও দেখা যেতে পারে।

প্রথমে অন্যান্য সব ইমপোর্টের সাথে prettyDOM ইমপোর্ট করে আনি।

```javascript
import { prettyDOM } from '@testing-library/dom'
```

```javascript
test('renders content', ()=> {
    const newQuest = {
        title: "Dampened Spirits",
        detail: "Put Maven Black-Briar's competition out of business."
    }

    const component = render(<Quest quest={newQuest} />)
    

    const title = component.container.querySelector('.title')

    console.log(prettyDOM(title))
})
```

