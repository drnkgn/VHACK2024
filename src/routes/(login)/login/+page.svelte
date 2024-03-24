<script>
    import { goto } from '$app/navigation';

    import AuthForm from '$lib/Auth/Form.svelte';
    import Button from '$lib/Button.svelte';
</script>

<AuthForm>
    <h1>Log In</h1>
    <div>
        <input type='email' placeholder='Email' />
        <input type='password' placeholder='Password' />
        <Button mode='light'>Log In</Button>
    </div>
    <p>or</p>
    <div>
        <Button
            to='/signup'
            mode='dark'
        >
            Create Account
        </Button>
    </div>
</AuthForm>

<style>
    div {
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
    div > :global(.Button) {
        width: 100%;
        margin: 8px 0px;
        height: 40px;
    }

    div > :global(.Button) {
        font-size: inherit;
        padding: 0px;
    }
</style>
