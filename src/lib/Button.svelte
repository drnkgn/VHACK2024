<script>
    export let to, mode, onClick;
</script>

{#if !to}
<button
    class={ `Button ${ mode }` }
    on:click={ onClick }
>
    <span>
        <slot />
    </span>
</button>
{:else}
<a
    class={ `Button ${ mode }` }
    href={ to }
    on:click={ onClick }
>
    <span>
        <slot />
    </span>
</a>
{/if}

<style>
    .Button {
        display: flex;
        justify-content: center;
        font-size: inherit;
        align-items: center;
        font-weight: bold;
        padding: 0.5em;
        cursor: pointer;
    }

    .light {
        border: 1px gray solid;
        color: black;
        background: white;
    }

    .dark {
        border: none;
        color: white;
        background: black;
    }

    .dark:hover {
        color: #dedede;
    }

    .light:hover {
        background: #dedede;
    }
</style>
