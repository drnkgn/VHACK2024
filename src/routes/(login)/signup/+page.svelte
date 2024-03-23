<script>
    import { goto } from '$app/navigation';
</script>

<div class='body'>
    <div class='panel'>
        <h1>Create an Account</h1>
        <form>
            <input type='email' placeholder='Email' />
            <input type='password' placeholder='Password' />
            <button>Create Account</button>
        </form>
        <p>or</p>
        <div>
            <button
                on:click={() => {
                    goto('/login');
                }}
            >
                Log In
            </button>
        </div>
    </div>
</div>

<style>
    .body {
        display: flex;
        width: 100%;
        height: calc(100% - var(--header-height));
        justify-content: center;
        align-items: center;
    }

    .panel {
        width: 25em;
        padding: 1em;
        border-radius: 0.5em;
        box-shadow: 0px 0px 5px gray;
    }

    form {
        display: flex;
        flex-direction: column;
    }

    h1, p {
        text-align: center;
    }

    p {
        margin: 0px;
    }

    input,
    button {
        width: 100%;
        margin: 8px 0px;
        height: 30px;
    }
</style>
