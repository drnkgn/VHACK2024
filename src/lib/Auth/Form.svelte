<form>
    <div class='panel'>
        <slot />
    </div>
</form>

<style>
    form {
        display: flex;
        width: 100%;
        height: calc(100% - var(--header-height));
        justify-content: center;
        align-items: center;
    }

    .panel {
        width: 25em;
        padding: 1em;
        box-shadow: 0px 0px 5px gray;
    }
</style>
