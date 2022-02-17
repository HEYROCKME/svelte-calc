
<script>
    export let id
    export let value
    export let handling
    
</script>


<button style:grid-area={id} id={id} value={value} on:click={handling}>{value}</button>


<style>
    button {
        min-width: 80px;
        min-height: 80px;
        font-size: 1.6em;
        margin: .1em;
        color: white;
        background-color: rgb(22, 18, 18);
        border: none;
        border-radius: 10px;
        box-shadow: 2px 2px 2px 1px rgba(74, 65, 65, 0.2);
       
    }

    button:hover, button:focus {
        background-color: aquamarine;
        transition-duration: .1s;
    }

     button:active {
        background-color: salmon;
        transition-duration: .1s;
    }
</style>