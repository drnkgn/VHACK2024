<script>
    export let position = '';
</script>

<div class={'nav-' + position}>
    <slot />
</div>

<style>
    .nav-left {
        display: flex;
        justify-content: flex-start;
        flex: 1;
    }

    .nav-mid {
        display: flex;
        justify-content: center;
        flex: 1;
    }

    .nav-right {
        display: flex;
        justify-content: flex-end;
        flex: 1;
    }
</style>

