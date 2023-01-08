<script lang="ts">
    export let initCount: number = 0
    export let maxCount;

    let count = initCount
    const increment = () => {
        if (count === maxCount) return
        count += 1
    }


    $:string = `hi ${count}`
    let string;

</script>

<button on:click={increment}>
    count is {count}
</button>
<p>{string}</p>
