<script>
  import Icon from "svelte-awesome";
  import Team from "../Team.svelte";
  import { faBars } from "@fortawesome/free-solid-svg-icons";
  import { faGithub } from "@fortawesome/free-brands-svg-icons";
</script>

<style>
  .uk-logo img {
    margin-right: 0.5em;
  }

  .uk-logo {
    font-size: 1.5em;
    font-family: "Noto Sans", sans-serif;
    color: #262229;
  }

  .uk-logo:hover {
    color: #a41f76;
  }

  #burger-menu {
    display: flex;
  }

  .uk-offcanvas-bar {
    background: white;
  }

  #icon-nav {
    margin-right: 0.5em;
  }

  .uk-navbar-container {
    background: white;
  }

  .uk-navbar-nav li a {
    color: #262229;
    display: none;
    position: relative;
    font-family: "Noto Sans", sans-serif;
  }

  .uk-offcanvas-bar .uk-nav li a,
  .uk-offcanvas-bar .uk-parent .uk-nav-sub li a {
    color: #262229;
    position: relative;
  }

  .uk-navbar-nav li a:hover,
  .uk-offcanvas-bar .uk-nav li a:hover,
  .uk-offcanvas-bar .uk-parent .uk-nav-sub li a:hover {
    color: #a41f76;
  }

  .uk-navbar-nav li a:focus,
  .uk-offcanvas-bar .uk-nav li a:focus,
  .uk-offcanvas-bar .uk-parent .uk-nav-sub li a:focus {
    color: #a41f76;
  }

  .uk-offcanvas-bar .uk-nav li.uk-parent span {
    color: #262229;
    font-size: 1.3em;
  }

  .uk-navbar-left .uk-navbar-nav li a::before,
  .uk-offcanvas-bar .uk-nav li a::before,
  .uk-nav-sub li a::before {
    content: "";
    position: absolute;
    width: 100%;
    height: 2px;
    bottom: 0;
    left: 0;
    background-color: #a41f76;
    visibility: hidden;
    transform: scaleX(0);
    transition: all 0.3s ease-in-out 0s;
  }
  .uk-navbar-left .uk-navbar-nav li a:hover::before,
  .uk-offcanvas-bar .uk-nav li a:hover::before,
  .uk-nav-sub li a:hover::before {
    visibility: visible;
    transform: scaleX(1);
  }

  /* On larger screens */
  @media only screen and (min-width: 960px) {
    #burger-menu {
      display: none;
    }

    .uk-navbar-container {
      background: rgba(255, 255, 255, 0.6);
      backdrop-filter: blur(1em) saturate(300%);
    }

    .uk-navbar-nav li a {
      display: flex;
      font-size: .9em;
    }

    .uk-nav li a {
      font-family: "Noto Sans", sans-serif;
      font-size: 1em;
    }
  }

  /*On extra-large screens*/
  @media only screen and (min-width: 2560px) {
    .uk-navbar-nav li a {
      font-size: 1.2rem;
    }

    .uk-nav li a {
      font-size: 1.2em;
    }

    .uk-logo {
      font-size: 1.75em;
    }
  }
</style>

<header>
  <div
    uk-sticky="sel-target: .uk-navabr-container; cls-active: uk-navbar-sticky">
    <nav class="uk-navbar-container" uk-navbar>

      <div class="uk-navbar-left">

        <a class="uk-navbar-item uk-logo" href="#">
          <img
            src="/assets/logo/Instrumentality-Logo.svg"
            alt=""
            width="32px" />
          Instrumentality
        </a>

        <ul class="uk-navbar-nav">
          <li>
            <a href="#team-modal" uk-toggle>Meet the team</a>
          </li>
          <li>
            <a>Follow us on</a>
            <div class="uk-navbar-dropdown">
              <ul class="uk-nav uk-navbar-dropdown-nav">
                <li>
                  <a href="https://github.com/instrumentality-foundation">
                    <span id="icon-nav">
                      <Icon data={faGithub} scale="1.2" />
                    </span>
                    GitHub
                  </a>
                </li>
              </ul>
            </div>
          </li>
        </ul>

      </div>

      <div class="uk-navbar-right">

        <ul class="uk-navbar-nav">
          <li>
            <a href="#offcanvas-navbar" id="burger-menu" uk-toggle>
              <Icon data={faBars} scale="1.5" />
            </a>
          </li>
        </ul>

      </div>
    </nav>
  </div>

  <!-- Off-canvas navbar for mobile phones -->
  <div id="offcanvas-navbar" uk-offcanvas="overlay: true; flip: true;">
    <div class="uk-offcanvas-bar uk-flex uk-flex-column">

      <ul class="uk-nav uk-nav-primary uk-nav-center uk-margin-auto-vertical">
        <li>
          <a href="#team-modal" uk-toggle>Meet the team</a>
        </li>
        <li class="uk-parent">
          <span>Follow us on:</span>
          <ul class="uk-nav-sub">
            <li>
              <a href="https://github.com/instrumentality-foundation">
                <span id="icon-nav">
                  <Icon data={faGithub} scale="1.2" />
                </span>
                GitHub
              </a>
            </li>
          </ul>
        </li>
      </ul>

    </div>
  </div>
</header>

<Team />