
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
        background-color: rgb(62, 54, 54);
        border: none;
        border-radius: 10px;
        box-shadow: 4px -4px 2px 0px aquamarine;
        /* transform: skewY(15deg); */
       
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