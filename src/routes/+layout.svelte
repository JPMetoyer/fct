



<script lang="ts">
    import { onMount } from "svelte";
    import "$lib/scss/app.scss";
    import { page } from '$app/stores';
    import Icon from "$lib/widgets/Icon.svelte";
    import { notification, sendNotification } from "$lib/functions/notifications";

    
    $: color = () => { 

        if ($notification === undefined) { return ""; }

        switch ($notification.type) {
            case "info":
                return "#3361FF";

            case "error":
                return "#FF5E6E";

            case "warning":
                return "#FF8800";

            case "success":
                return "#2BD84E";

            default:
                return "#3361FF";
        }
    }

    let showNavbar: boolean = false;
    const toggleNavbar = () => { showNavbar = !showNavbar };

    function addToggleNavbar(node: HTMLElement) {
        node.addEventListener(("click"), toggleNavbar);
    }

    onMount(async () => {

    }); 


    function scrollToSection(event) {
    event.preventDefault();
    const targetId = event.target.getAttribute('href').substring(1);
    const targetElement = document.getElementById(targetId);

    if (targetElement) {
      const offsetTop = targetElement.offsetTop - 70; 
      window.scrollTo({
        top: offsetTop,
        behavior: 'smooth'
      });
    }
  }


</script>

<svelte:head>
  <title>The Coding Initiative</title>
</svelte:head>


<nav>
    <a href="/" id="logo">
        <img src="/icons/fctherapy.jpg" alt="">
        <h1 style="color: app.$color-brand;
        text-decoration: none;
        font-weight: 700;
        margin-left: 1rem;
        font-size: 120%;">Full Circle Therapy</h1>
    </a>

    <div class="links">
        <a  href="/" on:click={scrollToSection}>Home</a>
        <a  href="/#about" on:click={scrollToSection}>About</a>
        <a  href="#services" on:click={scrollToSection}>Services</a>
        <a  href="#prices"on:click={scrollToSection}>Prices</a>

        
    </div>

    <span>

        
        <a href="https://secure.helloalma.com/providers/deandre-dyer/"  target="_blank" class="button"> Bookings</a>

       

        <Icon id="dropdown" handleClick={ toggleNavbar }>
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
                <path stroke-linecap="round" stroke-linejoin="round" d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5" />
              </svg>                                             
        </Icon>
    </span>
</nav>



    <slot></slot>



<section class={ showNavbar ? "show" : "" } id="popup-nav" use:addToggleNavbar>

    <div class="links">
        <a class={ $page.route.id === "/" ? "highlight" : "" } href="/">Home</a>
        <a class={ $page.route.id === "/" ? "highlight" : "" } href="/#about">About</a>
        <a class={ $page.route.id === "/" ? "highlight" : "" } href="/#services"> Services</a>
        <a class={ $page.route.id === "/" ? "highlight" : "" } href="/#prices">Prices</a>

        <div class="cite">
            <p>Copy &copy; 2024</p>
            <p>All rights reserved</p>
        </div>
    </div>

</section>

<section id="toast">
    <p style={ `background-color: ${ color() };` } class={ ($notification === undefined) ? "" : "show" }>{  ($notification === undefined) ? "" : $notification.message }</p>
</section>



<style lang="scss">
    @use "$lib/scss/variables" as app;

    


    nav {
        position: fixed; 
        top: 0px; 
        left: 0px; 
        right: 0px;
        z-index: 1002;

        display: flex; 
        align-items: center; 
        justify-content: space-between;

        background-color: #FAFAFC;
        backdrop-filter: blur(1rem);
        padding: 0.3rem 5vw; 

        a {

            h1 {
                color: app.$color-brand;
            }
            
        }

        &::after {
            position: absolute;

            content: "";
            bottom: 0px;
            left: 0vw;
            right: 0vw;
            height: 1px;
            border-bottom: 0.5px dashed app.$color-brand;
        }

        #logo {
            height: 2.8rem;
            fill: app.$color-brand;
            stroke: transparent;
            display: flex;
            align-items: center;
            justify-content: flex-start;
        }

        div.links {
            position: absolute;
            left: 50%;

            @media screen and (min-width: 940px) {
                display: flex;
            }

            display: none;
            align-items: center;
            justify-content: center;
            gap: 1rem;
            transform: translateX(-50%);

            a {
                border-bottom: 1px solid transparent; /* Invisible border */
                transition: all 240ms ease-in-out;
                &:hover {
                    border-bottom-color: app.$color-brand;
            }
            }
            
        }

        span {
            display: flex;
            align-items: center;
            justify-content: flex-end;
            gap: 0.8rem; 

           
        };

        

        
    }

    section#toast {
        z-index: 20;

        position: fixed;
        top: 0px;
        left: 0px;
        right: 0px;
        height: 100dvh;
        pointer-events: none;

        @keyframes show {
            0% {
                bottom: -20%;
            }

            20% {
                bottom: 2rem;
            }

            90% {
                bottom: 2rem;
            }
            100% {
                bottom: -20%;
            }
        }

        p {
            position: absolute;
            bottom: -20%;
            left: 50%;
            transform: translateX(-50%);

            width: max-content;
            max-width: 90vw;

            text-align: center;

            color: app.$color-background;
            box-shadow: 0rem 0rem 1.5rem rgba(40, 42, 54, 0.08);

            padding: 0.25rem 2rem;
            border-radius: 2rem;

            &.show {
                animation-name: show;
                animation-duration: 6000ms;
                animation-timing-function: linear;
                animation-fill-mode: forwards;
            }
        }
    }

    section#popup-nav {

            &.show {
                opacity: 100%;

                z-index: 100;
                > * { z-index: 101; }
            }
        

        

        display: block;
        opacity: 0%;

        transition-duration: 300ms;
        transition-property: opacity;
        transition-timing-function: ease-in;

        position: fixed;
        top: 0px;
        left: 0px;
        right: 0px;
        bottom: 0px;
        width: 100vw;
        height: 100vh;

        z-index: -1;
        > * { z-index: -1; }


        -webkit-backdrop-filter: blur(1rem);
        backdrop-filter: blur(1rem);
        background-color: rgb(255, 255, 255, 0.2);

        padding-top: 4rem;



        div.links {

            position: relative;

            height: 100svh;

            padding: 0px 5vw;

            display: flex;
            flex-direction: column; 
            align-items: flex-end;
            justify-content: center;
            gap: 0.5rem;

            transform: translateY(-4rem);

            div.cite {
                position: absolute;
                bottom: 0px;
                left: 0px;
                right: 0px;

                display: flex;
                align-items: center;
                justify-content: space-between;

                margin: 1rem 5vw;
            }

            > a {
                position: relative;
                font-size: 180%;
                font-weight: app.$weight-bold;

                padding: 0.5rem 0px 0.5rem 2rem;

            
            }

            
        }
    }

    
</style>






