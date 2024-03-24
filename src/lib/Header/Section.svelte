<script>
    export let position;
</script>

<div class={position}>
    <slot />
</div>

<style>
    .left {
        display: flex;
        justify-content: flex-start;
        flex: 1;
    }

    .mid {
        display: flex;
        justify-content: center;
        flex: 1;
    }

    .right {
        display: flex;
        justify-content: flex-end;
        flex: 1;
    }
</style>

