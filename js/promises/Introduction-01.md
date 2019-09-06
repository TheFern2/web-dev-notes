# What are promises, and why should you use them

Javascript is single threaded language, and so if you run a long running operations such as downloading a huge file, or just something that takes a while, the main UI will get blocked and unresponsive.

This is the reason why callbacks are used, and one of the main problems with callbacks, is that if you need to call one after another if even more than two or three, the code looks horrendous and unmanageable and unmaintainable.

If you are a web dev I am sure you know about callback hell but if you don't check it out [callbackhell.com](http://callbackhell.com/)

As Daniel Shiffman put it, host of "The Coding Train" [youtube channel](https://www.youtube.com/channel/UCvjgXvBlbQiydffZU7m1_aw) "Is there something better, well I don't know, but there is something", but don't take my words for it check out the [video](https://youtu.be/QO4NXhWo_NM?t=233)

Promises make the code cleaner, and easier to handle callbacks without losing your mind.

## Promises Example

So to be a bit upfront, I am not a web dev, and my JS experience is around 1% of what I do. Nevertheless I had this problem that I needed to solve, so I spent a few days learning about async code, and promises and it was fun. [Fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch) returns a [promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise), and you can also do your own functions to return a promise but more on that later.

```javascript
fetch(someUrl)
  .then(doSomethingUseful)
  .catch(anyErrors)
```

## My Problem

I needed to get all the refs (branches/tags) from a github repository using the github api, then get the dates of all refs, and finally sort from old to new. My code was horrible, and I was nesting callbacks inside callbacks, and occasionally the date was not fetched and sorting would fail. After learning how asynchronous code works, I needed to do the following:

- Call the api and get all refs for a particular repo
- Get the dates for all refs
- Sort refs by dates

```javascript
 var repoOwner = ''
 var repoName = ''
 const refsUrl = `https://api.github.com/repos/${repoOwner}/${repoName}/git/refs`

 fetch(refsUrl)
    .then(response => response.json()) // returns a promise and returns as json
    .then(json => console.log(json))   // prints json to console
    .catch(err => console.log(err))    // catches any errors
```

