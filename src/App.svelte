<script>
	import Calculator from './Calculator.svelte'
	import Display from './Display.svelte'
	import Button from './Button.svelte'
	import {keypads} from './Keypads.svelte';
	import {result} from './stores'
	
	let display

	const unsubscribe = result.subscribe(value => {
		display = value
	})

	
  


   

	const handleEvent = (event) => {
		const { target } = event
		const {value, className, id } = target
		console.log(className)

		
        switch (true) {
			case className.includes('digit') && id != "decimal":

			result.update(screen => screen += value)
			console.log(target + value)
				
				break;
		
			default:
			console.log("case not met")
				break;
		}

		// display += event.target.value
		// display = display
		
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



<style>
	:global(#display) {
		grid-area: display;
	}
	
</style>