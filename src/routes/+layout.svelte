<script lang="ts">
    import "$lib/scss/app.scss";

    const bookingUrl = "https://secure.helloalma.com/providers/deandre-dyer/";

    const links = [
        { href: "/#about", label: "About" },
        { href: "/#services", label: "Services" },
        { href: "/#prices", label: "Prices" }
    ];

    let menuOpen = false;
    let scrolled = false;

    const closeMenu = () => { menuOpen = false; };
</script>

<svelte:head>
    <title>Full Circle Therapy</title>
    <meta name="description" content="Full Circle Therapy PLLC — Counseling & Trauma Services, Consulting & School Services. Spring, TX.">
</svelte:head>

<svelte:window on:scroll={ () => scrolled = window.scrollY > 8 } on:keydown={ (e) => e.key === "Escape" && closeMenu() } />

<header class:scrolled class:open={ menuOpen }>
    <div class="container bar">
        <a href="/" class="brand" on:click={ closeMenu }>
            <img src="/icons/fctherapy.jpg" alt="" width="63" height="44">
            <span>Full Circle Therapy</span>
        </a>

        <nav aria-label="Main">
            { #each links as link }
                <a href={ link.href }>{ link.label }</a>
            { /each }
        </nav>

        <div class="actions">
            <a href={ bookingUrl } target="_blank" rel="noopener" class="button small book">Book an appointment</a>

            <button class="menu-toggle" aria-label={ menuOpen ? "Close menu" : "Open menu" } aria-expanded={ menuOpen } aria-controls="mobile-menu" on:click={ () => menuOpen = !menuOpen }>
                <span></span><span></span>
            </button>
        </div>
    </div>

    <div id="mobile-menu" class="mobile-menu" hidden={ !menuOpen }>
        <div class="container">
            { #each links as link }
                <a href={ link.href } on:click={ closeMenu }>{ link.label }</a>
            { /each }
            <a href={ bookingUrl } target="_blank" rel="noopener" class="button" on:click={ closeMenu }>Book an appointment</a>
        </div>
    </div>
</header>

<slot></slot>

<style lang="scss">
    @use "$lib/scss/variables" as app;

    header {
        position: sticky;
        top: 0;
        z-index: 50;

        background-color: rgba(255, 255, 255, 0.82);
        -webkit-backdrop-filter: saturate(160%) blur(14px);
        backdrop-filter: saturate(160%) blur(14px);
        border-bottom: 1px solid transparent;
        transition: border-color 200ms ease, box-shadow 200ms ease;

        &.scrolled, &.open {
            border-bottom-color: app.$color-shade;
            box-shadow: 0 6px 24px rgba(20, 38, 58, 0.05);
        }

        &.open {
            background-color: app.$color-background;
        }
    }

    .bar {
        display: flex;
        align-items: center;
        justify-content: space-between;
        gap: 1.5rem;
        height: 4.75rem;
    }

    .brand {
        display: flex;
        align-items: center;
        gap: 0.75rem;
        flex-shrink: 0;

        img {
            width: 3.9rem;
            height: 2.75rem;
            object-fit: cover;
            border-radius: 0.6rem;
        }

        span {
            font-family: app.$typeface-heading;
            font-size: 1.2rem;
            font-weight: app.$weight-bold;
            color: app.$color-brand-deep;
            letter-spacing: -0.01em;
        }
    }

    nav {
        display: flex;
        align-items: center;
        gap: 2.25rem;

        a {
            position: relative;
            font-size: 0.95rem;
            font-weight: app.$weight-semibold;
            color: app.$color-midground;
            transition: color 160ms ease;

            &::after {
                content: "";
                position: absolute;
                left: 0;
                right: 0;
                bottom: -0.35rem;
                height: 2px;
                border-radius: 2px;
                background-color: app.$color-accent;
                transform: scaleX(0);
                transition: transform 200ms ease;
            }

            &:hover {
                color: app.$color-foreground;
                &::after { transform: scaleX(1); }
            }
        }

        @media (max-width: 860px) {
            display: none;
        }
    }

    .actions {
        display: flex;
        align-items: center;
        gap: 0.5rem;
    }

    .book {
        @media (max-width: 560px) {
            display: none;
        }
    }

    .menu-toggle {
        display: none;
        position: relative;
        width: 2.75rem;
        height: 2.75rem;
        border-radius: 0.75rem;

        &:hover { background-color: app.$color-elevate; }

        span {
            position: absolute;
            left: 0.75rem;
            right: 0.75rem;
            height: 2px;
            border-radius: 2px;
            background-color: app.$color-foreground;
            transition: transform 220ms ease, top 220ms ease;

            &:nth-child(1) { top: 1.05rem; }
            &:nth-child(2) { top: 1.6rem; }
        }

        @media (max-width: 860px) {
            display: block;
        }
    }

    header.open .menu-toggle span {
        &:nth-child(1) { top: 1.33rem; transform: rotate(45deg); }
        &:nth-child(2) { top: 1.33rem; transform: rotate(-45deg); }
    }

    .mobile-menu {
        border-top: 1px solid app.$color-shade;
        padding: 0.75rem 0 1.5rem;

        .container {
            display: flex;
            flex-direction: column;
        }

        a:not(.button) {
            padding: 0.9rem 0;
            border-bottom: 1px solid app.$color-shade;
            font-family: app.$typeface-heading;
            font-size: 1.35rem;
            color: app.$color-foreground;
        }

        .button {
            margin-top: 1.25rem;
            width: 100%;
        }

        @media (min-width: 861px) {
            display: none;
        }
    }
</style>
