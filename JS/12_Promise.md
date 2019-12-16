# **Promise**


A promise is an object that may produce a single value  in the future: either a resolved or reject value(a reason that it’s not resolved (e.g., a network error occurred). A promise may be in one of 3 possible states: fulfilled, rejected, or pending. 


![Prototype](https://www.nearform.com/wp-content/uploads/2019/02/Blog-img-01-1024x427.png)

<!-- Promise users can attach callbacks to handle the fulfilled value or the reason for rejection. -->



Let's understand with example:-


```js
// If condition is true

const flip = new Promise((resolve, reject) => {
  if (true) {
    resolve('success');
  } else {
    reject('failure');
  }
});

flip
  .then(result => console.log('result', result))
  .catch(error => console.log('error', error));

console.log('after flip');


// after flip
// result success
```  


```js
// If condition is false

const clean = new Promise((resolve, reject) => {
  if (false) {
    resolve('Cleaned Successfully');
  } else {
    reject('Not Cleaned');
  }
});

clean
  .then(result => console.log('result', result))
  .catch(error => console.log('error', error));

console.log('Cleaning must be completed');

// Cleaning must be completed
// error Not Cleaned

```


