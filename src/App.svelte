<script>
    import Button from "./lib/Button.svelte";
    import IoIosArrowDropdown from 'svelte-icons/io/IoIosArrowDropdown.svelte'

</script>

<Button on:click|once={(event) => {
    alert(true)
}
} let:x >
    <div style:width="20px">
        <IoIosArrowDropdown slot="left"></IoIosArrowDropdown>
    </div>
    Button Test {x}</Button>
<style>
</style>
