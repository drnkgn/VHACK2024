<script>
    export let show;
</script>

<div class='dropdown'>
    <nav style:opacity={show ? 1 : 0}>
        <div class='frame'
             style:opacity={show ? 1 : 0}
             style:margin-left={show ? '1em' : '0.5em' }>
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
    opacity: 0;
    transition: opacity 0.3s ease-in-out;
}

.dropdown {
    position: fixed;
    display: flex;
    top: 5em;
    width: 100%;
    justify-content: center;
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
