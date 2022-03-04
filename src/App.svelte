<script>
	import Calculator from './Calculator.svelte'
	import Display from './Display.svelte'
	import Button from './Button.svelte'
	import {keypads} from './Keypads.svelte';
	import {result} from './stores'
	
	let display
	$: updateDisplay = display

	
	let init = true

	


	result.subscribe(value => {
		display = value
	})
	
   const checkInit = (value) => {

   }

   const updateScreen = (value) => {
	if (init)  {
		result.set("")
		init = false
	}
	result.update(screen => screen += value ) 
	    
	
   }

   const clearAll = () => {
	   result.set("0")
   }

   const handleOperator = (value) => {
	console.log("operator " + value)	
	updateScreen(value)
   }


   const handleEquals = () => {
	   
	let expression = display.replace(/(^0*)/,"")
	console.log(expression)
   }

   const handleDecimal = (decimal) => {
	   console.log(decimal)
	   updateScreen(decimal)
   }

   const handleDigit = (clicked) => {
	  
	 updateScreen(clicked)
   }

   const handleZero = (zero) => {

   }

   const calculate = () => {

   }

	const handleEvent = (event) => {
		const { target } = event
		const {value, className, id } = target		
		
        switch (true) {
			case className.includes('digit') && id != "decimal":

			value === "0" ?  handleZero(value) : handleDigit(value)  

			console.log(value, "display " + display)
			  break;
			
			case className.includes('operator') :	
			  handleOperator(value)
			  break
		
			case value === "CLR" :
			  console.log("clear")
			  clearAll()
			  break

			case className.includes("equals") :
			  handleEquals()
			  break
			
			case className.includes("decimal") :
			  handleDecimal(value)
			  break


			default:
			console.log("case not met")
				break;
		}		
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
	:global(body) {
		background-color: salmon;
	}
	
</style>