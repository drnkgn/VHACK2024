<script>
    import Header from '$lib/Header/Header.svelte';
    import HeaderSection from '$lib/Header/Section.svelte';
    import Dropdown from '$lib/Header/Dropdown.svelte';
    import Footer from '$lib/Header/Footer.svelte';

    import Link from '$lib/Link.svelte';

    const links = [
        { 
            name: 'products',
            dropdown: true,
            items: [
                'Crop Protection',
                'Seeds & Traits',
                'Biologicals',
                'Digital Solutions',
                'Seed Treatments',
                'Forages',
            ]
        },
        { name: 'news', dropdown: false },
        { name: 'about us', dropdown: false },
        { name: 'resources', dropdown: false }
    ];

    let showDropdown = false;
    let currentActive = 0;
</script>

<Header>
    <HeaderSection position='left'>
        Crop Management System
    </HeaderSection>
    <HeaderSection position='mid'>
    {#each links as link, index}
        const links = [
        { 
            name: 'products',
            dropdown: true,
            items: [
                'Crop Protection',
                'Seeds & Traits',
                'Biologicals',
                'Digital Solutions',
                'Seed Treatments',
                'Forages',
            ]
        },
        { name: 'news', dropdown: false },
        { name: 'about us', dropdown: false },
        { name: 'resources', dropdown: false }
    ];
    {/each}
    </HeaderSection>
    <HeaderSection position='right'>
        <a>Get Started</a>
        <a href='/login'>Log In</a>
    </HeaderSection>
</Header>
<Dropdown show={showDropdown} items={links[currentActive].items} />
<slot />
<Footer />

<style>
    a {
        border: 1px gray solid;
        margin: 0.5em;
    }
</style>
