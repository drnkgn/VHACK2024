<script>
    import { goto } from '$app/navigation';
    
    import AuthForm from '$lib/Auth/Form.svelte';
    import Button from '$lib/Button.svelte';
</script>

<AuthForm>
    <h1>Sign Up</h1>
    <div>
        <input type='email' placeholder='Email' />
        <input type='password' placeholder='Password' />
        <Button mode='light'>Create Account</Button>
    </div>
    <p>or</p>
    <div>
        <Button
            to='/login'
            mode='dark'
        >
            Log In
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
