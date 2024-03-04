<div class="container">
    <div class="cabinet">
        <div></div>
        <div></div>
        <div></div>
    </div>
    <div class="pasta"></div>
    <div class="vent">
        <div></div>
    </div>
    <div class="hang">
        <div class="cup"></div>
        <div class="cup"></div>
        <div class="cup"></div>
    </div>
    <div class="oven">
        <div class="display">
            <button on:mousedown={startIncrement} on:mouseup={stopIncrement} on:mouseleave={stopIncrement}>+</button>
            <button on:mousedown={startDecrement} on:mouseup={stopDecrement} on:mouseleave={stopDecrement}>-</button>
            <p>{temp}°</p>
        </div>
        <div class="mid"><img src={fire} alt="FLAMME" id="flameFire"></div>
    </div>
    <div class="table">
        <div></div>
        <div></div>
        <div></div>
    </div>
    <div class="line"></div>
    <div class="washer">
        <div></div>
        <div></div>
        <div></div>
    </div>
    <div class="plate"></div>
    <div class="pot">
        <div class="smoke"></div>
    </div>
</div>

<style>
    @import '../app.css';
</style>

<script>
    import fire from "../images/fire.png";

    let temp = 0;
    let incrementInterval;
    let decrementInterval;

    function startIncrement() {
        increment();
        incrementInterval = setInterval(increment, 10);
    }

    function stopIncrement() {
        clearInterval(incrementInterval);
    }

    function startDecrement() {
        decrement();
        decrementInterval = setInterval(decrement, 10);
    }

    function stopDecrement() {
        clearInterval(decrementInterval);
    }

    function increment() {
        temp += 1;
        updateFlame();
        updateSmoke()
    }

    function decrement() {
        if (temp > 0)
            temp -= 1;
        updateFlame();
        updateSmoke()
    }

    function updateFlame() {
        let flame = document.getElementById("flameFire");
        if (flame) {
            flame.style.opacity = (temp / 1000).toString();
        }
    }

    function updateSmoke() {
        let smoke = document.querySelector(".smoke");
        if (smoke) {
            smoke.style.animationDuration = `${1000 / temp}s`;
        }

        if (temp === 6969) {
            
        }
    }

</script>
