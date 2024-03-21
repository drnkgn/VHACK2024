<script>
    import Header from "$lib/Header/Header.svelte"
    import Footer from "$lib/Header/Footer.svelte"
</script>

<Header />
<slot />
<Footer />

<style>
:global(*) {
    box-sizing: border-box;
}

:global(body) {
    margin: 0px;
}
</style>
