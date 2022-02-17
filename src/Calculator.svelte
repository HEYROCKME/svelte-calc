<div id="calculator" class="calulator">
    <slot>
        Here goes the calculator parts
    </slot>
</div>


<style>
    div {
        margin: 0 auto;
        padding: 1em;
        width: 50%;
        min-width: 300px;
        height: 60vh;
        min-height: 500px;
        background-color: rgb(47, 46, 46);
        border-radius: 10px;

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

    }
</style>