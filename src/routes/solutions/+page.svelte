<script src="https://cdn.jsdelivr.net/npm/chart.js">
    import Header from '$lib/Header/Header.svelte';
    import HeaderSection from '$lib/Header/Section.svelte';

    let links = [
            { name: 'Tab 1', dropdown: false},
            { name: 'Tab 2', dropdown: false },
            { name: 'Tab 3', dropdown: false },
            { name: 'Tab 4', dropdown: false }
        ];
</script>

<div class="Section">
    <Header>
        <HeaderSection position="left">
            {#each links as link, index}
            <div class = "box">
                <a href="{link.name}">{link.name}</a>
            </div>
            {/each}
        </HeaderSection>
    </Header>
    <br>
    <div class = "top-component">
        <div class = "plant-condition">
            <h6>Crop Health</h6><br>
            <h3>Healthy</h3>
        </div>
        <div class = "weather-condition">
            <h6>Weather condition</h6><br>
            <h3>Rainy</h3>
        </div>
        <div class = "pest-outbreak">
            <h6>Pest Outbreaks</h6><br>
            <h3>Contained</h3>
        </div>
    </div>
    <br>
    <div class = "middle-component">
        <div class = "graph">

        </div>
        <div class = "author">
            <canvas id="myChart"></canvas>
        </div>
    </div>
    <script>
    import { onMount } from 'svelte';
        const data = {
            labels: ["Jan", "Feb", "Mar", "Apr", "May"],
            datasets: [{
                label: "Dollar Unit",
                data: [100, 200, 300, 400, 500],
                borderColor: "blue",
                borderWidth: 1
            }]
        };

        const options = {
            scales: {
                x: {
                    type: 'time',
                    time: {
                        unit: 'month'
                    },
                    position: 'bottom'
                },
                y: {
                    type: 'linear',
                    position: 'left',
                    ticks: {
                        callback: function(value, index, values) {
                            return '$' + value;
                        }
                    }
                }
            }
        };

        const ctx = document.getElementById('myChart').getContext('2d');
        const myChart = new Chart(ctx, {
            type: 'line',
            data: data,
            options: options
        });

        // Initialize the chart after the component mounts
    onMount(() => {
        const ctx = document.getElementById('myChart').getContext('2d');
        new Chart(ctx, {
            type: 'line',
            data: data,
            options: options
        });
    });
    </script>
</div>


<style>
.box {
    display: inline-block;
    padding: 10px;
    margin-right: 10px;
    background-color: #ccc;
    border: 1px solid #000;
}

.box a {
    text-decoration: none;
    color: #000;
}

.top-component{
    display : flex;
    max-width: 100vw;
    max-height: 10vw;
    margin-left: 76px;
}

.plant-condition, .weather-condition, .pest-outbreak {
    flex-grow: 1;
    border: 2px solid #000; /* Border with black color */
    padding: 10px; /* Add padding to the content */
    max-width: 25vw;
    border-radius: 10px; /* Rounded corners */
    margin: 20px; /* Add space between the two boxes */
}

.plant-condition {
    background-color: #aaf0aa; /* Light green background color */
}

.weather-condition {
    background-color: #8a2be2; /* Blueish-purple background color */
}

.plant-condition h6,
.weather-condition h6,
.pest-outbreak h6,
.plant-condition h3,
.weather-condition h3,
.pest-outbreak h3 {
    margin: 0; /* Reset default margin */
}

.plant-condition h6,
.weather-condition h6,
.pest-outbreak h6 {
    display: block; /* Ensure <h6> elements are displayed as block elements */
    margin-bottom: 5px; /* Add margin below <h6> elements for spacing */
}

.plant-condition h3,
.weather-condition h3,
.pest-outbreak h3 {
    display: block; /* Ensure <h3> elements are displayed as block elements */
}

</style>
