<script>
// import { afterUpdate } from 'svelte';
// import {result} from './stores'

export let displayValue
export let id


// afterUpdate(() => {
//     const unsubscribe = result.subscribe(value => {
// 		display = value
// 	})
// });






	

</script>


<!-- <div id={id}>{displayValue}</div> -->
<input id={id} type="text" bind:value={displayValue} />

<style>

    input {
        height: 75px;
        background-color: rgb(34, 33, 33);
        color:white;
        display: block;
        padding: 1em;
        text-align: right;
        font-size: 1.6em;
        border: none;
        border-radius: 10px;
        box-shadow: inset 0px 0 10px 10px black ;
        margin-bottom: .2em;
        max-width: 370px;
        overflow: hidden;
        /* transform: skewY(  15deg) */

    }

</style>