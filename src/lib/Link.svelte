<script>
    export let to, underline, mouse, styles;
</script>

<span
    class='link'
    style={styles}
    on:mouseenter={mouse != null ? mouse.enter : null}
    on:mouseleave={mouse != null ? mouse.leave : null}
>
    <a href={to}><slot /></a>
    {#if underline}
    <div class='link-line' />
    {/if}
</span>

<style>
    a {
        text-decoration: none;
        text-transform: capitalize;
    }

    .link:hover .link-line {
        width: 100%;
    }

    .link-line {
        width: 0%;
        border-bottom: 1px black solid;
        transition: width 0.3s ease-in-out;
    }
</style>
