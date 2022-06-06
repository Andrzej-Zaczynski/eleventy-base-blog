---
layout: layouts/post.njk
title: the Document Object Model
templateClass: tmpl-post
eleventyNavigation:
  key: the Document Object Model
  order: 4
---


<div class="container">
  <h1>Todo</h1>

  <form id="todo">
    <label for="title">Title</label>
    <input type="text" name="title" id="title" required>
    <label for="priority">Priority</label>
    <select name="priority" id="priority">
      <option value="low">Low</option>
      <option value="medium" selected>Medium</option>
      <option value="high">High</option>
    </select>
    <button>Add</button>
  </form>

  <!--This is an empty container for use by javascript.-->
  <ul id="todo-pane"></ul>

  <footer>
    <small>
      Flag images used with thanks from <a href="https://www.iconfinder.com/iconsets/prettyoffice8">https://www.iconfinder.com/iconsets/prettyoffice8</a>.
    </small>
  </footer>
</div>

body {
  font-family: sans;
  line-height: 1.5;
}

/* Limit the maximum width regardless of window size */
.container {
  max-width: 60em;
  margin-left: auto;
  margin-right: auto;
}

/* The form */
#todo {
  border: solid thin darkgray;
  padding: 1.5em;
  border-radius: 0.25em;
}

/* The unordered list containing the todos */
#todo-pane {
  padding: 0;
}

/* The todos themselves */
#todo-pane li {
  display: flex;
  max-width: 20em;
  align-items: center;
  background-color: lightyellow;
  border: thin orange solid;
  border-radius: 0.25em;
  padding: 0.5em;
  margin: 1em 0;
}

/* A todo that was just created */
.just-created {
  box-shadow: 0 0 20px 1px orange;
}

/* The image of a flag within a todo */
#todo-pane li img {
  width: 1em;
  padding-right: 1rem;
}

/* The small text in the footer */
small {
  font-size: small;
  font-style: italic;
}

```diff-js
// Store the URL of an image for each priority level.
const priorityImages = {
  low:
    "https://cdn1.iconfinder.com/data/icons/prettyoffice8/256/Flag-green.png",
  medium:
    "https://cdn1.iconfinder.com/data/icons/prettyoffice8/256/Flag-yellow.png",
  high: "https://cdn1.iconfinder.com/data/icons/prettyoffice8/256/Flag-red.png"
};

// Get the form by ID from the forms collection.
const form = document.forms.todo;
// Get the todo pane (the 'ul' element) to insert todos into.
const todoPane = document.getElementById("todo-pane");
// Get the text input for the title. We'll read from this when creating the todo.
const titleInput = form.elements.title;
// Get the priority select element. We'll read from this when creating the todo.
const prioritySelect = form.elements.priority;
// Get a *live* list of all elements with the 'todo' class.
const allTodos = document.getElementsByClassName("todo");

// Add an event listener that will
// 1. Create a new todo. The details should come from the form.
// 2. Insert it into the DOM.
// 3. Clear the title input ready to create a new todo note.
// 4. Prevent the default behaviour (ie don't submit to a server).

form.addEventListener("submit", function (event) {
  for (const todo of allTodos) {
    todo.classList.remove("just-created");
  }

  const newTodo = createTodo(titleInput.value, prioritySelect.value);
  todoPane.appendChild(newTodo);
  titleInput.value = "";
  event.preventDefault();
});

function createTodo(title, priority) {
  // Create the text node with the variable 'title'.
  const textNode = document.createTextNode(title);
  // Create a new list item element to contain the text node.
  const todo = document.createElement("li");

  // Optional extra 1:
  // Add an image for the priority. The URLs are stored in the priorityImages object.
  const image = document.createElement("img");
  image.src = priorityImages[priority];
  todo.appendChild(image);

  // Add the text node to the list item element.
  todo.appendChild(textNode);

  // The most recently created list item (only!) should have the 'just-created' class.
  const listItem = document.querySelector(".just-created");

  // Optional extra 2:
  // Add a click handler to the note that deletes it on click using Element.remove().
  todo.addEventListener("click", function (event) {
    event.currentTarget.remove();
  });

  // Return the new element.
  return todo;
}
```
