<div id="calculator" class="calulator">
    <slot>
        Here goes the calculator parts!
    </slot>
</div>


<style>
    div {
        margin: 5em auto 0 ;
        padding: 1em;
        width: 50%;
        min-width: 300px;
        height: 60vh;
        min-height: 500px;
        background-color: rgb(68, 64, 59);
        border-radius: 10px;
        box-shadow: 
          20px -20px 1px 0px rgb(39, 41, 40),
          15px -15px 1px 0px rgb(39, 41, 40),
          10px -10px 1px 0px rgb(39, 41, 40),
          5px -5px 1px 0px rgb(39, 41, 40)
          ;
        
        display: grid;
        grid-template-columns: repeat(4 x 1fr);
        grid-template-rows: repeat(5 x 1fr);
        grid-template-areas: 
        "display display display display"
        "clear clear divide multiply"
        "seven eight nine add"
        "four five six subtract"
        "one two three equals"
        "zero zero decimal equals"
        ;
        transform: skewY(15deg)
    }
</style>