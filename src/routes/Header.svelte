<script>
    import Dropdown from './Dropdown.svelte'

    const links = [
        { name: 'products', dropdown: true },
        { name: 'solutions', dropdown: true },
        { name: 'blog', dropdown: false },
        { name: 'about', dropdown: false }
    ];

    let active = false;
</script>

<header>
    <nav>
        <div class='nav-left'>
            LOGO HERE
        </div>
        <div class='nav-mid'>
            {#each links as link}
                <div class='nav-links'
                     on:mouseenter={() => {
                         if (link.dropdown) { active = true; }
                     }}
                     on:mouseleave={() => {
                         if (link.dropdown) { active = false; }
                     }}>
                    <a href='/{link.name}'>{link.name}</a>
                    <div class='link-line'/>
                </div>
            {/each}
        </div>
        <div class='nav-right'>
            <button>Get Started</button>
            <button>Log In</button>
        </div>
    </nav>
</header>
{#if true}
    <Dropdown show={active}>
        <p>Hi</p>
    </Dropdown>
{/if}

<style>
button {
    border: 1px gray solid;
    background: none;
}

header {
    display: flex;
    height: 5em;
    justify-content: center;
    border: 1px black solid;
}

nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 90%;
}

a {
    text-decoration: none;
    text-transform: capitalize;
}

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

.nav-right > button {
    margin: 0.5em;
}

.nav-links {
    margin: 1em;
}

.nav-links:hover .link-line {
    width: 100%;
}

.link-line {
    width: 0%;
    border-bottom: 1px black solid;
    transition: width 0.3s ease-in-out;
}
</style>
