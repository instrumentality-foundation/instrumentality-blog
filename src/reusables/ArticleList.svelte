<script>
    import Lazy from 'svelte-lazy';

    import A20200620 from "../articles/A20200620.svelte";
</script>

<style>
    .uk-section {
        background: white;
        padding: 2em;
    }

    .uk-flex {
        align-items: center;
    }
</style>

<section class="uk-section uk-flex uk-flex-column uk-flex-center">
    <Lazy height={500}>
        <A20200620 />
    </Lazy>
</section>