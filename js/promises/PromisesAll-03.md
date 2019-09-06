## Promise.all()

Promise.all takes an array of promises and awaits for all promises to return. 

```javascript
let promises = [___, ___, ___]
Promise.all(promises)
.then...
.catch...
```

One thing to note is that if one promise returns an error, none of the promises will return at all. So it is useful to handle potential errors with try/catch.

