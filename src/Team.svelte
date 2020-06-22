<script>

</script>

<style>
    .uk-flex-center {
        align-items: center;
    }

    .uk-modal-body div img {
        border-radius: 15%;
    }

    @media only screen and (min-width: 960px) {
        .uk-modal-body div p {
            font-size: 1.1em;
        }
    }
</style>

<div id="team-modal" uk-modal>
    <div class="uk-modal-dialog">
        <button class="uk-modal-close-default" type="button" uk-close></button>

        <div class="uk-modal-header">
            <h2 class="uk-modal-title uk-text-center">The Instrumentality team</h2>
        </div>

        <div class="uk-modal-body" uk-overflow-auto>
            <div class="uk-flex uk-flex-column uk-flex-center">
                <img width="200px" height="200px" src="/assets/images/team/Alexandru.webp" alt="Alexandru">
                <h3>Alexandru Balan</h3>
                <p>Happily married to a wonderful woman. Linux enthusiast, software developer and hacker of all things. Creator of Instrumentality and main developer.</p>
            </div>
        </div>

    </div>
</div>