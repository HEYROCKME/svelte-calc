<script>
	import Calculator from './Calculator.svelte'
	import Display from './Display.svelte'
	import Button from './Button.svelte'
	import {keypads} from './Keypads.svelte';
	import {result} from './stores'
	
	let display
	$: updateDisplay = display

	const unsubscribe = result.subscribe(value => {
		display = value
	})

	
  

   const updateScreen = (value) => {
	   display === "0" ? result.set("") : null
	result.update(screen => screen += value)
   }

   const clearAll = () => {
	   result.set("0")

   }

	const handleEvent = (event) => {
		const { target } = event
		const {value, className, id } = target
		

		
        switch (true) {
			case className.includes('digit') && id != "decimal":

			updateScreen(value)
			
			break;
			
			case className.includes('operator') :	
			console.log("operator " + value)
			break
		
			case value ==="CLR" :
			console.log("clear")
			clearAll()

   
			break

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
		<Display id="display" displayValue={updateDisplay} />

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