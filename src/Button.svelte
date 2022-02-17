
<script>
    export let id
    export let value
    export let handling
</script>


<button id={id} value={value} on:click={handling}>{value}</button>