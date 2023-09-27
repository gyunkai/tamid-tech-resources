---
marp: true
theme: gaia
class: invert
---

<!-- _class: lead -->

# Web Dev 101

---

## Quiz & Review

### True or False

Web Structuring Section

- Web pages are stored on the client computer.

- We usually call the home page "home.html".

---

HTML Section

- HTML is a programming language.
- HTML tags don't have to come in pairs.
- `<title></title>` is placed in the `<head></head>` section.
- You use `<link></link>` to create a hyperlink.
- `<h1></h1>` is the largest heading tag.

---

CSS Section

- CSS is used to style HTML.
- `.xxx` is used to select an element by its ID.
- You need JavaScript to use CSS.

---

JS Section

- `==` and `===` are the same.
- JS differences between `let`, and `const`.
- JS has int and float.
- You must have `;` at the end of each line.
- You must write `;` at the end of each line.
- Use `console.log()` to print to the console.

---

<!-- _class: lead -->

## Set up your dev tools

- Make sure you have an editor (We are using VSCode here, but you can be like "I use vim BTW"), a terminal, and a browser installed and set up.

---

## Create your first website

### Set up the files

**_Hands on time!_**

Let's do it fully inside a terminal.

- Create a folder called `my-first-website`
- Create a file called `index.html` inside the folder
- Create a file called `style.css` inside the folder
- Create a file called `script.js` inside the folder

---

### Serving the files

Like we said, we need a browser to see our website. But we also need a server to serve our files.

In this case, we will be starting a server on our computer.

Live Server is a VSCode extension that will serve our files for us.

**_Hands on time!_**

- Install Live Server
- Start the server

---

### HTML

**_Hands on time!_**

- Open `index.html` in your editor
- add a basic HTML template
- add a title
- add a heading "Hello World!"

Now you can see your website in the browser! How cool is that!

A great resource I recommend everyone to use for looking up any HTML tags as well as CSS and JavaScript syntax is [W3CSchools](https://www.w3schools.com)

---

Let's add more things to the simple web page.

Add a `<img/>`

Add a `<Button></Button>` That says "Press me"

---

<!-- _class: lead -->

## CSS

### CSS Selectors

CSS's syntax is very simple. It's just a selector followed by a list of rules.

---

Element selector

```css
p {
}
```

Class selector

```css
.this-is-a-class {
}
```

ID selector

```css
#id {
}
```

---

_More selector usage, you can check W3CSchools._

We use different selectors for different abstraction level of our styling.

And how do we apply the styles to the html

```css
<p class="class-a class-b class-c" id="myP1"></p>
```

An HTML element can have multiple classes, but only one id

---

#### CSS Rules

There are tons of CSS rules out there, you don't have to remember all of them.

Some examples of rules you will see everyday:

```text
background-color: defines the background color of an element.
color: defines the color of an element.
border: a shorthand(collection) of border styles
margin: defines the margin of an element.
padding: defines the padding of an element.
```

---

Everything in CSS is a box!

For things that are not shaped like a box like texts, think of it as always having a imaginary box containing it.

**_Hands on time!_**

Let's make a colorful webpage!

- Add background color to the headings you have.
- Change the padding and margin to make the webpage more readable.

---

<!-- _class: lead-->

# JavaScript

JavaScript is the only way (for now) for the client browser to be interactive and can fetch data dynamically.
