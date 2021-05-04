# একটি সম্পূর্ণ টেস্ট \(A complete test suite\)



```javascript
const supertest = require('supertest')
const app = require('../app');
const api = supertest(app);

//models
const Blog = require('../models/blog')
const mongoose = require('mongoose')

//do something before starting to run test
beforeAll(() => {
    //....
    //....
})

//Alternatively, do something before running each test
beforeEach(()= > {
    //...
    //...
})

//define tests in groups
describe('get', () => {
test('gets all blog', async () => {
                const login = await api.post('/api/login').send({
            "name":"Rosalia Hargitt",
            "username":"rhargitt4",
            "password":"MePH7BJ2I"});
            
            const token = login.body.token;
        const posts = await helper.getAllPosts();
        const count = posts.length;
       const response = await api.get('/api/blogs').set('Authorization', 'bearer ' + token);
       // console.log(response.body);
       expect(response.body).toHaveLength(count);
})
});

//do something after all test has run
//like closing the connection or resetting the DB
afterAll(()=> {
        mongoose.connection.close();
    })
```

