<script>
    import Header from "./Header.svelte"
    import Footer from "./Footer.svelte"
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
