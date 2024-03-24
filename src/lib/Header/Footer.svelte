<script>
    import Link from '$lib/Link.svelte';

    import DiscordIcon from '$lib/Icons/Discord.svelte';
    import TwitterIcon from '$lib/Icons/Twitter.svelte';
    import LinkedInIcon from '$lib/Icons/LinkedIn.svelte';
    import YoutubeIcon from '$lib/Icons/Youtube.svelte';

    const items = [
        'Contact Us',
        'Corporate Website',
        'Careers',
        'Accessibility'
    ];
</script>

<footer>
    <div class='inner'>
        <div class='left'>
            <h1>CropManager</h1>
            <div>
                <p>Connect with us through:</p>
                <section class='social'>
                    <DiscordIcon />
                    <TwitterIcon />
                    <LinkedInIcon />
                    <YoutubeIcon />
                </section>
            </div>
        </div>
        <div class='right'>
            <section class='links'>
            {#each items as item}
                <Link to='' underline={true}>{item}</Link>
            {/each}
            </section>
        </div>
    </div>
</footer>

<style>
    footer {
        height: 22em;
        background: black;
        padding: 2em 10em;
    }

    h1, p {
        color: white;
    }

    .inner {
        display: flex;
    }

    .left {
        width: 40em;
        border-right: 1px gray solid;
    }

    .right {
        display: flex;
        flex-direction: column;
        width: 100%;
    }

    .social {
        display: flex;
        align-items: center;
    }

    .social > :global(svg) {
        margin: 0px 5px;
    }

    .links {
        display: flex;
        flex-direction: column;
        align-items: end;
        margin: 21.44px 0px;
    }

    .inner :global(.Link) {
        padding: 0.5em;
    }

    .inner :global(.Link-Text) {
        color: white;
        font-weight: bold;
    }

    .inner :global(.Link-Line) {
        border-bottom: 1px white solid;
    }
</style>
