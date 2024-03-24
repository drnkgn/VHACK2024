<script>
    import Header from '$lib/Header/Header.svelte';
    import HeaderSection from '$lib/Header/Section.svelte';
</script>

<Header>
    <HeaderSection position='left'>
        <span>CropManager</span>
    </HeaderSection>
</Header>
<slot />

<style>
    span {
        font-weight: bold;
    }
</style>
