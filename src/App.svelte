<script>
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

    $: console.log(todos)
</script>

<h2>{todos.length}</h2>
<TodoList bind:todos></TodoList>
<button on:click={() => {todos = [];}}>Update Todos</button>

<style>
</style>
