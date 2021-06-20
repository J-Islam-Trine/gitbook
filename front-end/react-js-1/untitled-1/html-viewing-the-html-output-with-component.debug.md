# কম্পোনেন্টের HTML আউটপুট দেখা \(Viewing the HTML output with component.debug\)

টেস্টের নিচের দিকে যুক্ত করতে হবে - 

```javascript
test('renders content', ()=> {
       const newQuest = {
        title: "Dampened Spirits",
        detail: "Put Maven Black-Briar's competition out of business."
    }

    const component = render(<Quest quest={newQuest} />)

    component.debug()

    //expect(component.container.querySelector('.detail')).toHaveTextContent('Put Maven Black-Briar\'s competition out of business.')
})
```

আউটপুট হবে নিচের মত - 

```javascript
console.log
    <body>
      <div>
        <div
          class="quests"
        >
          <h2
            class="title"
          >
            Dampened Spirits
          </h2>
          <p>
            Put Maven Black-Briar's competition out of business.
          </p>
        </div>
      </div>
    </body>
```

