## Creating a function that returns a promise

```javascript
function someFunction(anArgument){
    return new Promise((resolve, reject) => {
        // some sanity checks to reject the promise
        if(isNaN(anArgument)){
            reject(new Error('A number is required!'))
        } else{
            // some code goes here
            anotherFunction(resolve, anArgument)
        }    
    });
}
```

## Using syntax sugar (Async/Await)

In addition to creating functions that return promises, there are syntax suger keywords, which can make code readability even cleaner. By leveraging await, each await call will return a promise asynchronously until is done, and then proceed to the next line

```javascript
async function someAsyncFunction(){
    let response = await fetch(someUrl)
    let json = await response.json()
    //... and so on    
    // can also return an object or value as any other function
}
```

