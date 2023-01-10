<svelte:options immutable={true}/>

<script lang="ts">
    import {createEventDispatcher} from "svelte";


    export let todos = []

    let inputText = ''

    const dispatch = createEventDispatcher()

    const handleSubmit = () => {
        dispatch('addtodo', {
            title: inputText
        }, {cancelable: true})
        inputText = ''
    }

    const handleRemoveTodo = (id: string) => {
        dispatch('removetodo', {id})
    }

    const handleToggleTodo = (id, value) => {
        dispatch('toggletodo', {id, value})
    }
</script>

<div>
    <ul>
        {#each todos as {id, title, completed} (id)}
            <li>
                <label>
                    <input type="checkbox"
                           on:input={event => {event.currentTarget.checked = completed
                            handleToggleTodo(id, !completed)
                           }}
                           checked={completed}>
                    {title}
                </label>
                <button on:click={()=>handleRemoveTodo(id)}>Remove</button>
            </li>
        {/each}
    </ul>
    <form on:submit|preventDefault={handleSubmit}>
        <input bind:value={inputText}/>
        <button type="submit" disabled={!inputText}>Add</button>
    </form>
</div>

