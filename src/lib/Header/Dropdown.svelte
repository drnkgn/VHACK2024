<script>
    export let show;
</script>

<div
    class='dropdown'
    on:mouseenter={() => { show = true; }}
    on:mouseleave={() => { show = false; }}
    style:visibility={show ? 'visible' : 'hidden'}
    style:opacity={show ? 1 : 0}
>
    <nav>
        <div
            class='frame'
            style:opacity={show ? 1 : 0}
            style:margin-left={show ? '1em' : '0.5em'}
        >
            <div class='title'>
                <h1>Title</h1>
            </div>
            <slot />
        </div>
    </nav>
</div>

<style>
    nav {
        background: white;
        width: 30%;
        height: 100%;
        border: 1px red solid;
    }

    .dropdown {
        position: fixed;
        display: flex;
        top: 3em;
        width: 100%;
        padding-top: 2em;
        justify-content: center;
        transition: visibility 0.4s,
                    opacity 0.3s ease-in-out;
    }

    .frame {
        display: flex;
        margin: 1em;
        margin-left: 0.5em;
        opacity: 0;
        transition: opacity 0.3s ease-in-out 0.1s,
                    margin-left 0.3s ease-in-out;
    }

    .title {
        width: 10em;
        height: 10em;
        border: 1px black solid;
    }
</style>
