<script>
    import Link from '$lib/Link.svelte';

    export let show, items;
</script>

<div
    class='dropdown'
    on:mouseenter={() => { show = true; }}
    on:mouseleave={() => { show = false; }}
    class:visible={show}
    class:opaque={show}
>
    <nav>
        <div
            class='frame'
            class:opaque={show}
        >
            <h1>Title</h1>
            <div class='items'>
            {#each items as item}
                <Link underline={true} styles='padding: 0.3em'>{item}</Link>
            {/each}
            </div>
        </div>
    </nav>
</div>

<style>
    nav {
        background: white;
        width: fit-content;
        height: 100%;
        border: 1px red solid;
        transition: width 0.3s ease-in-out;
    }

    .dropdown {
        visibility: hidden;
        position: fixed;
        display: flex;
        top: 3em;
        width: 100%;
        padding-top: 2em;
        opacity: 0;
        justify-content: center;
        transition: visibility 0.4s,
                    opacity 0.3s ease-in-out;
    }

    .frame {
        margin: 1em;
        opacity: 0;
        transition: opacity 0.3s ease-in-out 0.1s;
    }

    .items {
        display: grid;
        grid-template-rows: repeat(3, 1fr);
    }

    .title {
        width: 10em;
        height: 10em;
        border: 1px black solid;
    }

    .opaque {
        opacity: 1;
    }

    .visible {
        visibility: visible;
    }
</style>
