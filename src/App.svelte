<script>
	import Calculator from './Calculator.svelte'
	import Display from './Display.svelte'
	import Button from './Button.svelte'
	import {keypads} from './Keypads.svelte';

	let display = ""


	function handleEvent(event) {
		console.log(event.target.value)
		display += event.target.value
		display = display
	}
</script>
  

<main>

	<Calculator>
		<Display id="display" displayValue={display} />

		   {#each keypads as keypad}
		  <Button value={keypad.value} className={keypad.class} id={keypad.id} handling={(e) => handleEvent(e)} />
		 {/each}
		

</Calculator>
</main>



