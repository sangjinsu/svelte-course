<script lang="ts">
    import TodoList from "./lib/TodoList.svelte";
    import {v4 as uuid} from "uuid";

    let todos = [
        {
            id: uuid(),
            title: 'Todo1',
            completed: false
        }, {
            id: uuid(),
            title: 'Todo1',
            completed: false
        }, {
            id: uuid(),
            title: 'Todo1',
            completed: false
        }, {
            id: uuid(),
            title: 'Todo1',
            completed: false
        }
    ]

    const handleAddTodo = (event) => {
        event.preventDefault()
        todos = [...todos, {
            id: uuid(),
            title: event.detail.title,
            completed: false
        },]
    }

    const handleRemoveTodo = (event) => {
        todos = todos.filter(todo => todo.id !== event.detail.id)
    }

    const handleToggleTodo = (event) => {
        todos = todos.map(todo => {
            if (todo.id == event.detail.id){
                return {...todo, completed: event.detail.value}
            }
            return {...todo}
        })
    }

</script>

<h2>{todos.length}</h2>
<TodoList {todos} on:addtodo={handleAddTodo}
          on:removetodo={handleRemoveTodo}
          on:toggletodo={handleToggleTodo}
></TodoList>

<style>
</style>
