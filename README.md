# Todo App
This is a short todo list app used for demoing the basics of Vue.js 3.x. A user can add todo items to the todo list. Once the user completes those todo items, they can check them off and they will be added to the completed todo list. The user also has the option of deleting a todo item.

## Components 
In the root component, App.vue, the todo input, todo list, and completed list composed in the template. 

```javascript
<template>
  <Header/>
  <div id="todoInputContainer">
    <input id="todoInput" v-model="todoInput"/>
    <button id="todoAddBtn" v-on:click="handleAdd">Add</button>
  </div>
  <div id="container">
    <TodoList 
      v-bind:todoList="todoList" 
      v-bind:handleCompleted="handleCompleted"
      v-bind:handleDelete="handleDelete"/>
    <CompletedList 
      v-bind:completedList="completedList"/>
  </div>
</template>
```

The state of the todo and completed list are added to the return of the data property in the root component and passed down to each respective component.
## Adding todo items
When the user wants to add a todo, they type their note in the input just below the header and click the add button. In code, the input is tracked using the `v-model` directive. When the add button is pressed, the `handleAdd` function is called which add the user input to `todoList` and clears `todoInput`.

```javascript
handleAdd() {
  this.todoList.push({id: this.todoList.length, content: this.todoInput})
  this.todoInput = '';
}
```

Each todo has a simple id used to keep track of each item, which is important for completing and deleting items.
## Completeing todo items
Once the user completed a todo, they can click the check next to the associated todo and it will be added to the completed todo list. The `handleCompleted` function handles this logic by checking the todo list for the todo item's id that matchs the target id associated with the todo item the user clicked on. The target item is also removed from `todoList` and added to `completedList` at the same time.

```javascript
handleCompleted(e) {
  this.todoList = this.todoList.filter(item => {
    if (item.id === Number(e.target.id)) {
      this.completedList.push(item);
      return false;
    } else {
      return true;
    }
  })
}
```

## Removing todo items
Removing items from `todoList` is similar to completing items. In this case, the item is found and just removed from `todoList`.

```javascript
handleDelete(e) {
  this.todoList = this.todoList.filter(item => item.id !== Number(e.target.id))
}
```

## Author
Denzal Martin

## References 
[Vue documentation](https://v3.vuejs.org/guide)

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
