<script>
    export let title;
    export let link;
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

    .uk-button {
        width: 70%;
        background: white;
        border-radius: .5em;
    }

    .uk-flex {
        align-items: center;
    }

    button a {
        text-decoration: none;
        color: #262229;
        font-family: 'Noto Sans', sans-serif;
        font-size: 1em;
    }

    button a:hover {
        color: #a41f76;
    }

    /*On large screens*/
    @media only screen and (min-width: 960px) {
        h1 {
            font-size: 2.5em;
        }

        .uk-button {
            width: 45%;
        }

        button a {
            font-size: 1.2em;
        }
    }

    /*On larger screens*/
    @media only screen and (min-width: 1200px) {
        h1 {
            font-size: 3em;
        }

        .uk-button {
            width: 30%;
        }

        button a {
            font-size: 1.2em;
        }
    }

    /*On extremely large devices*/
    @media only screen and (min-width: 2560px) {
        h1 {
            font-size: 3.5em;
        }

        button a {
            font-size: 1.8em;
        }
    }
</style>

<div class="uk-flex uk-flex-column" id="announcement-banner">
    <h1 class="uk-text-center">{title}</h1>

    <button class="uk-button uk-button-large uk-margin-xlarge-top">
        <a href={link}>Read everything about it</a>
    </button>
</div>