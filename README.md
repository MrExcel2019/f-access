# f-access
<h1 align="center">f-access</h1>

f-access is a tool mainly used to catalogue schedules  of work, time and breaks 
## What you get
-


## How to use
```bash
npm install --save f-access
```

```js
const f-access = require('f-access');
const document = `
<p class="paragraph highlighted-text" >
  My name is <b> MrExcel. </b> and I am a <span class="work"> software developer </span>
</p>
<div class = "container" id="container" >
 <b> What is the name of this module </b>
 <p> What is the name of this libray </p>
 <a class="myWebsite" href="https://www.mexcel.xyz" > My website </a>
</div>
<form>
  <label for="name"> What's your name? </label>
  <input type="text" id="name" name="name" />
</form>
`;
const dom = new f-access(document);
```

## API 
Methods on the document object.
- document.getElementsByTagName()
- document.getElementsByClassName()
- document.getElementsByName()
- document.getElementById()
- document.querySelectorAll()
- document.querySelector()

Methods on the HTML node object
- node.getElementsByClassName()
- node.getElementsByTagName()
- node.querySelector()
- node.querySelectorAll()
- node.getAttribute()

Properties of the HTML node object
- node.outerHTML
- node.innerHTML
- node.textContent
- node.innerText

Their usage is as they are expected to be used in an actual HTML DOM with the desired method parameters.

## Examples for document object

```js

let paragraphNodes = dom.getElementsByTagName('p');
// returns a list of node objects with node name 'p'

let nodesWithSpecificClass = dom.getElementsByClassName('work');
// returns a list of node objects with class name 'work'

let nodeWithSpecificId = dom.getElementById('container');
// returns a node with id 'container'

let complexQueryNodes = dom.querySelectorAll('p.paragraph b');
// returns a list of nodes that satisfy the complex query of CSS selectors

let nodesWithSpecificName = dom.getElementsByName('name');
// returns a list of nodes with the specific 'name'

let linkNode = dom.querySelector('a#myWebsite');
// returns a node object with with the CSS selector

let linkHref = linkNode.getAttribute('href');
// returns the value of the attribute e.g 'https://www.ajah.xyz'

let linkInnerHTML = linkNode.innerHTML
// returns the innerHTML of a node object e.g ' My website '

let linkTextContent = linkNode.textContent 
// returns the textContent of a node object e.g ' My website '

let linkInnerText = linkNode.innerText
// returns the innerText of a node object e.g ' My website '

let linkOuterHTML = linkNode.outerHTML
// returns the outerHTML of a node object i.e. '<a class="myWebsite" href="https://www.mexcel.xyz" > My website </a>'

```


## Examples for a node object

```js

let paragraphNodes = dom.getElementsByTagName('p');
// returns a list of node objects with node name 'p'

let nodesWithSpecificClass = paragraphNodes[0].getElementsByClassName('work');
// returns a list of node objects inside the first paragraph node with class name 'work' 


let complexQueryNodes = paragraphNodes[0].querySelectorAll('span.work');
// returns a list of nodes in the paragraph node that satisfy the complex query of CSS selectors


let linkNode = dom.querySelector('a#myWebsite');
// returns a node object with with the CSS selector

let linkHref = linkNode.getAttribute('href');
// returns the value of the attribute e.g 'https://www.mexcel.xyz'

let linkInnerHTML = linkNode.innerHTML
// returns the innerHTML of a node object e.g ' My website '

let linkTextContent = linkNode.textContent 
// returns the textContent of a node object e.g ' My website '

let linkInnerText = linkNode.innerText
// returns the innerText of a node object e.g ' My website '

let linkOuterHTML = linkNode.outerHTML
// returns the outerHTML of a node object i.e. '<a class="myWebsite" href="https://www.mexcel.xyz" > My website </a>'

```


## Contributing
In case you have any ideas, features you would like to be included or any bug fixes, you can send a PR.

(Requires Node v6 or above)
- Clone the repo

```bash
git clone https://github.com/MrExcel2019/f-access.git
```
