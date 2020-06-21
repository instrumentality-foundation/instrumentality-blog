<script>
    export let title;
</script>

<style>
    #announcement-banner {
        width: 95%;
    }

    h1 {
        font-family: 'Noto Sans', sans-serif;
        color: white;
        font-size: 1.7em;
    }

    span {
        background: white;
        border-radius: .5em;
        padding: 1em 3em 1em 3em;
    }

    .uk-flex {
        align-items: center;
    }

    span a {
        text-decoration: none;
        color: #262229;
        font-family: 'Noto Sans', sans-serif;
        font-size: 1em;
    }

    span a:hover {
        color: #a41f76;
    }

    /*On large screens*/
    @media only screen and (min-width: 960px) {
        h1 {
            font-size: 2.5em;
        }

        span a {
            font-size: 1.2em;
        }
    }

    /*On larger screens*/
    @media only screen and (min-width: 1200px) {
        h1 {
            font-size: 3em;
        }

        span a {
            font-size: 1.2em;
        }
    }

    /*On extremely large devices*/
    @media only screen and (min-width: 2560px) {
        h1 {
            font-size: 3.5em;
        }

        span a {
            font-size: 1.8em;
        }
    }
</style>

<div class="uk-flex uk-flex-column" id="announcement-banner">
    <h1 class="uk-text-center">{title}</h1>

    <span class="uk-margin-xlarge-top">
        <a href="#article-card" uk-scroll>Find the story bellow</a>
    </span>
</div>