<script>
    export let to, underline, mouse, styles;
</script>

<span
    class='Link'
    style={styles}
    on:mouseenter={mouse != null ? mouse.enter : null}
    on:mouseleave={mouse != null ? mouse.leave : null}
>
    <a class='Link-Text' href={to}><slot /></a>
    {#if underline}
    <div class='Link-Line' />
    {/if}
</span>

<style>
    a {
        text-decoration: none;
        text-transform: capitalize;
    }

    .Link {
        display: inline-block;
        width: fit-content;
    }

    .Link:hover .Link-Line {
        width: 100%;
    }

    .Link-Text {
        white-space: nowrap;
    }

    .Link-Line {
        width: 0%;
        border-bottom: 1px black solid;
        transition: width 0.3s ease-in-out;
    }
</style>
