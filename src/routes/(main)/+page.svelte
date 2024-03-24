<script>
    import Section from '$lib/Landing/Section.svelte';
    import Button from '$lib/Button.svelte';
    import Product from '$lib/Assets/product.jpeg';
    import Crop from '$lib/Assets/background.jpg';
</script>

<Section>
    <h1>Solve problems, drive profitability</h1>
    <p>
        Crop Management is the easiest way for farmers and their
        advisors to collaboratively plan, grow and analyze each field. Harness
        the power of your data to boost yield and protect the bottom line.
    </p>
    <div class='panel'>
        <Button mode='light' to=''>Get Started</Button>
    </div>
</Section>
<Section>
    <h1>Benefits to Growers</h1>
    <div class='panel-img'>
        <p>
            Based on a few simple inputs, CropManager can provide
            any level of irrigation and fertilization decision
            support in order to vlidate or improve your existing
            operation production and increase your overall
            confidence.
        </p>
        <img src={Product} />
    </div>
</Section>
<Section>
    <h1>Why CropManager?</h1>
    <p>Make confident decisions with data-driven insights:</p>
    <div class='panel-img'>
        <div class='collage'>
            <img src={Crop} />
            <ul style='border-left: 1px gray solid'>
                <li>
                    Get the most value from your investment with field-by-field
                    plans that tailor variety and hybrid, rate and placement to
                    every acre you plant
                </li>
                <li>
                    Simplify collaboration with your advisors by working from a
                    single, shared tool
                </li>
                <li>
                    Set up seed for optimal performance with recommended planter
                    settings and seeding recommendations based on your yield
                    targets, seed price, and grain price
                </li>
            </ul>
        </div>
    </div>
</Section>

<style>
    ul {
        margin: 0px 2em;
    }

    p {
        padding-right: 3em;
    }

    .panel {
        padding: 1em 0px;
        display: flex;
        justify-content: center;
    }

    .panel-img {
        display: flex;
    }

    .panel-img img {
        width: 30em;
    }

    .collage {
        display: flex;
    }

    .collage img {
        width: 15em;

    }
</style>
