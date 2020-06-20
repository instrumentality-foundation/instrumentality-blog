<script>
    export let image = "/assets/images/placeholder.jpg";
    export let title = "Placeholder title";
    export let description = "This is a placeholder description";
</script>

<style>
    .uk-card-media-top img {
        object-fit: cover;
        width: 100%;
        height: 30vh;
    }

    .uk-button {
        color: #262229;
        font-family: 'Noto Sans', sans-serif;
        background: white;
        font-size: 1em;
        border: 1px solid #f3665b;
        transition: 0.3s all ease-in-out;
    }

    .uk-button:hover {
        background: #f3665b;
        color: white;
    }

    /*On larger devices*/
    @media only screen and (min-width: 960px) {
        .uk-card-media-top img {
            height: 50vh;
        }
    }
</style>

<div class="uk-card uk-card-default uk-margin-bottom">

    <div class="uk-card-media-top">
        <!-- Card header -->
        <img src={image} alt="A placeholder">
    </div>

    <div class="uk-card-body">
        <h3 class="uk-card-title">{title}</h3>
        <p>{description}...</p>
        
        <div class="uk-flex uk-flex-center">
            <button class="uk-button" uk-toggle="target: #full-article" type="button">Read more</button>
        </div>

    </div>

</div>

<div id="full-article" class="uk-modal-container" uk-modal>

    <div class="uk-modal-dialog">

        <div class="uk-modal-header">
            <h2 class="uk-modal-title uk-text-center">{title}</h2>
        </div>

        <div class="uk-modal-body" uk-overflow-auto>
            <button class="uk-modal-close-default" type="button" uk-close></button>
            <slot></slot>
        </div>
    </div>

    
</div>