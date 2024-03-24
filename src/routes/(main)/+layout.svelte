<script>
    import Header from '$lib/Header/Header.svelte';
    import HeaderSection from '$lib/Header/Section.svelte';
    import Dropdown from '$lib/Header/Dropdown.svelte';
    import Footer from '$lib/Header/Footer.svelte';
    import Button from '$lib/Button.svelte';

    import Link from '$lib/Link.svelte';

    const links = [
        { name: 'products', dropdown: false },
        { name: 'news', dropdown: false },
        { name: 'about us', dropdown: false },
        { name: 'resources', dropdown: false }
    ];

    let showDropdown = false;
    let currentActive = 0;
</script>

<Header>
    <HeaderSection position='left'>
        <span>CropManager</span>
    </HeaderSection>
    <HeaderSection position='mid'>
    {#each links as link, index}
        <Link
            to={link.name}
            styles='padding: 1em;'
            underline={true}
            mouse={
                link.dropdown
                    ? {
                        enter: () => {
                            showDropdown = true;
                            currentActive = index;
                        },
                        leave: () => {
                            showDropdown = false;
                        }
                      }
                    : null
            }
        >
            {link.name}
        </Link>
    {/each}
    </HeaderSection>
    <HeaderSection position='right'>
        <Button to='/login' mode='dark'>Log In</Button>
    </HeaderSection>
</Header>
<slot />
<Footer />

<style>
    span {
        font-weight: bold;
    }

    a {
        font-weight: bold;
        color: white;
        padding: 0.5em;
        background: black;
    }

    :global(.Link-Text) {
        color: black;
    }
</style>
