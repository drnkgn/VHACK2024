<script>
    export let links;
</script>

<header class='Header'>
    <nav>
        <slot />
    </nav>
</header>

<style>
    header {
        display: flex;
        height: var(--header-height);
        justify-content: center;
    }

    nav {
        display: flex;
        justify-content: space-between;
        align-items: center;
        width: 90%;
    }
</style>
