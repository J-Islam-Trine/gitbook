# এক্সাম্পল কম্পোনেন্ট ও টেস্ট ফাইল \(Example component with it's test file\)

{% code title="quest.jsx" %}
```javascript
const Quest = ({quest}) => {


    return(
        <div className='quests'>
             <h2 className='title'>{quest.title}</h2>
             <p className='detail'>{quest.detail}</p>
           </div>
    )
}
```
{% endcode %}

{% code title="quest.test.js" %}
```javascript
import React from 'react'
import '@testing-library/jest-dom/extend-expect'
import { render } from '@testing-library/react'
import Quest from './singleQuest'

test('renders content', ()=> {
    const newQuest = {
        title: "Dampened Spirits",
        detail: "Put Maven Black-Briar's competition out of business."
    }

    const component = render(<Quest quest={newQuest} />)

    //component.debug()

    expect(component.container).toHaveTextContent('Put Maven Black-Briar\'s competition out of business.')
})
```
{% endcode %}

