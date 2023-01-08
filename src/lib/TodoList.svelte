<script>
    import {v4 as uuid} from "uuid";

    export let todos = []

    let inputText = ''
    const handleSubmit = () => {
        if (!inputText) {
            return
        }
        // todos.push(
        //     {
        //         id: uuid(),
        //         completed: false ,
        //         title: inputText
        //     }
        // )
        // todos = todos
        todos = [...todos, {
            id: uuid(),
            completed: false,
            title: inputText
        }]
        inputText = ''
    }
</script>

<div>
    <ul>
        {#each todos as {id, title}, index (index)}
            <li>{index + 1} - {title}</li>
        {/each}
    </ul>
    <form on:submit|preventDefault={handleSubmit}>
        <input bind:value={inputText}/>
        <button type="submit" disabled={!inputText}>Add</button>
    </form>
</div>

