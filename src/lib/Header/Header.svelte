<script>
    import Dropdown from '$lib/Header/Dropdown.svelte'
    import Section from '$lib/Header/Section.svelte'

    const links = [
        { name: 'products', dropdown: true },
        { name: 'solutions', dropdown: true },
        { name: 'blog', dropdown: false },
        { name: 'about', dropdown: false }
    ];

    let showDropdown = false;
</script>

<header>
    <nav>
        <Section position={'left'}>
            LOGO HERE
        </Section>
        <Section position={'mid'}>
            {#each links as link}
                {#if link.dropdown}
                    <div
                        class='nav-links'
                        on:mouseenter={() => { showDropdown = true; }}
                        on:mouseleave={() => { showDropdown = false; }}
                    >
                        <a href='/{link.name}'>{link.name}</a>
                        <div class='link-line'/>
                    </div>
                {:else}
                    <div class='nav-links'>
                        <a href='/{link.name}'>{link.name}</a>
                        <div class='link-line'/>
                    </div>
                {/if}
            {/each}
        </Section>
        <Section position={'right'}>
            <button>Get Started</button>
            <button>Log In</button>
        </Section>
    </nav>
</header>
<Dropdown show={showDropdown}>
    <ul>
        <li>Seeds & Traits</li>
        <li>Crop Protection</li>
        <li>Biologicals</li>
        <li>Digital Solutions</li>
        <li>Seed Treatments</li>
        <li>Forages</li>
    </ul>
</Dropdown>

<style>
    button {
        border: 1px gray solid;
        background: none;
        margin: 0.5em;
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

    .nav-links {
        padding: 1em;
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
