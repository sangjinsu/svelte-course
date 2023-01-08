<script>
    let x
</script>

<button on:click class="flex bg-red-500 hover:bg-red-700 text-white font-bold py-2 px-4 rounded" {...$$restProps}>
    {#if $$slots.left}
        <div>
            <slot name="left"></slot>
        </div>
    {/if}
    <slot x={x}>Fallback</slot>
</button>