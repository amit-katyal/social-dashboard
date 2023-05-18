// Clicking on same label to switch toggle

One possible solution is to use JavaScript to toggle a class on the body element that changes the CSS variables for the light and dark mode colors. You can also use a checkbox input and a label element to create the toggle switch. Here's an example of how you can do that:

```html
<!-- HTML -->
<body>
  <div class="toggle-container">
    <input id="switch" type="checkbox" name="theme" />
    <label for="switch">Dark Mode</label>
  </div>
</body>
```

```css
/* CSS */
:root {
  /* light mode colors */
  --bg-color: white;
  --text-color: black;
  --shadow-color: gray;
}

.dark-mode {
  /* dark mode colors */
  --bg-color: black;
  --text-color: white;
  --shadow-color: darkgray;
}

body {
  padding: 25px;
  background-color: var(--bg-color);
  color: var(--text-color);
}

.toggle-container {
  display: flex;
  align-items: center;
}

input[type="checkbox"] {
  display: none;
}

label {
  cursor: pointer;
  position: relative;
}

label::before {
  content: "";
  display: block;
  width: 50px;
  height: 25px;
  border-radius: 15px;
  background-color: var(--shadow-color);
}

label::after {
  content: "";
  position: absolute;
  top: 2px;
  left: 2px;
  width: 21px;
  height: 21px;
  border-radius: 50%;
  background-color: var(--text-color);
}

input:checked + label::after {
  transform: translateX(25px);
}
```

```javascript
// JavaScript
const checkbox = document.getElementById("switch");
const body = document.body;

checkbox.addEventListener("change", function () {
  body.classList.toggle("dark-mode");
});
```

Source:
(1) Light/Dark Theme Toggle with CSS and JavaScript — CodeHim. https://www.codehim.com/vanilla-javascript/light-dark-theme-toggle-with-css-and-javascript/.
(2) How To Toggle Between Dark and Light Mode - W3Schools. https://www.w3schools.com/howto/howto_js_toggle_dark_mode.asp.
(3) 20 Best Toggle Switches [Pure CSS Examples] - Alvaro Trigo. https://alvarotrigo.com/blog/toggle-switch-css/.
(4) How to create Light / Dark mode toggle with CSS and Javascript. https://www.simpleweblearning.com/how-to-create-light-dark-mode-toggle-with-css-and-javascript/.
(5) Dark/ Light Theme Toggle Switch Using HTML,CSS & JavaScript. https://www.codewithrandom.com/2022/12/23/toggle-switch-css-dark-mode-dark-light-toggle-switch-codewihhrandom/.
