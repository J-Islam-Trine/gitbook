# সিলেক্টর দিয়ে টেস্ট করা \(testing an element with it's selector\)

আমাদের কম্পোনেন্টের HTML এলিমেন্টগুলোতে যদি className এট্রিবিউট দেয়া থাকে তাহলে আমরা সরাসরি সেটার জন্যই টেস্ট করতে পারি।

```javascript
test('renders content', ()=> {
    const newQuest = {
        title: "Dampened Spirits",
        detail: "Put Maven Black-Briar's competition out of business."
    }

    const component = render(<Quest quest={newQuest} />)

    //component.debug()

    expect(component.container.querySelector('.detail')).toHaveTextContent('Put Maven Black-Briar\'s competition out of business.')
})
```

