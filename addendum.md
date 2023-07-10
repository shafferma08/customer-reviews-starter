
**Addendum:** 

Greetings students, I would like to add an important clarification regarding a piece of code we discussed in this video. We talked about these two lines:

```javascript
// let tableInfo = document.getElementsByTagName("article");
// tableInfo.insertAdjacentHTML("beforeEnd", reviewCode);
```

In our example, this code didn't work as expected. The reason is that `document.getElementsByTagName("article")` actually returns an HTMLCollection, which is an array-like object of all elements with the tag name "article". So, when you attempt to call `insertAdjacentHTML` on `tableInfo`, it doesn't work because `tableInfo` is a collection of elements, not a single element.

In other words, if you want to manipulate a specific element from the HTMLCollection, you must specify its index. Here's how you'd use an index to access the first article element:

```javascript
document.getElementsByTagName("article")[0].insertAdjacentHTML("beforeEnd", reviewCode);
```

Now, you might be wondering, "What if I only have one `article` element on my page? Can't I just select it directly?" Yes, you can! If there's only one `article` element, you can use `document.querySelector("article")` to select it. This method returns the first element within the document that matches the specified selector. So, you could rewrite the code as:

```javascript
let tableInfo = document.querySelector("article");
tableInfo.insertAdjacentHTML("beforeEnd", reviewCode);
```

In summary, it's important to remember that methods like `getElementsByTagName` return a collection of elements. Even if you only expect one element, you'll need to use an index to access it. On the other hand, `querySelector` returns a single element, making it a great choice when you know there's only one matching element on the page.

I hope this clarification helps you understand these DOM manipulation methods a little better. Happy coding!
