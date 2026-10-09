<section id="hero">
    <div class="container grid">
        <div class="copy">
            <h1>
                Your Journey <em>Today</em><br>
                Your Triumph <em>Tomorrow</em>
            </h1>

            <ul class="offerings">
                <li>Counseling &amp; Trauma Services</li>
                <li>Consulting &amp; School Services</li>
            </ul>

            <div class="cta">
                <a href="https://secure.helloalma.com/providers/deandre-dyer/" target="_blank" rel="noopener" class="button">Book an appointment</a>
                <a href="#services" class="button outline">Our services</a>
            </div>
        </div>

        <div class="visual">
            <svg class="ring" viewBox="0 0 400 400" aria-hidden="true">
                <path d="M60 300 A170 170 0 0 1 300 60" fill="none" stroke="currentColor" stroke-width="10" stroke-linecap="round"/>
            </svg>
            <img src="/images/landingimage.jpeg" alt="A therapist and a child smiling together during a play therapy session" width="1080" height="675">
        </div>
    </div>
</section>

<style lang="scss">
    @use "$lib/scss/variables" as app;

    #hero {
        position: relative;
        overflow: hidden;
        padding: 4.5rem 0 6rem;
        background:
            radial-gradient(60rem 30rem at 85% 0%, app.$color-brand-soft 0%, transparent 70%),
            radial-gradient(40rem 24rem at 0% 100%, app.$color-accent-soft 0%, transparent 70%),
            app.$color-background;

        @media (max-width: 900px) {
            padding: 2.5rem 0 4.5rem;
        }
    }

    .grid {
        display: grid;
        grid-template-columns: 1fr 1.1fr;
        align-items: center;
        gap: 4rem;

        @media (max-width: 900px) {
            grid-template-columns: 1fr;
            gap: 3rem;
        }
    }

    h1 {
        font-size: clamp(2.5rem, 5.6vw, 4.25rem);
        line-height: 1.05;
        letter-spacing: -0.025em;
        color: app.$color-brand-deep;

        em {
            font-style: italic;
            font-weight: app.$weight-regular;
            color: app.$color-brand;
        }
    }

    .offerings {
        list-style: none;
        margin: 2rem 0 2.5rem;
        display: flex;
        flex-direction: column;
        gap: 0.65rem;

        li {
            display: flex;
            align-items: center;
            gap: 0.75rem;
            font-size: 1.1rem;
            font-weight: app.$weight-semibold;
            color: app.$color-foreground;

            &::before {
                content: "";
                flex-shrink: 0;
                width: 0.6rem;
                height: 0.6rem;
                border-radius: 50%;
                background-color: app.$color-accent;
                box-shadow: 0 0 0 4px app.$color-accent-soft;
            }
        }
    }

    .cta {
        display: flex;
        flex-wrap: wrap;
        gap: 0.75rem;
    }

    .visual {
        position: relative;

        img {
            position: relative;
            width: 100%;
            aspect-ratio: 5 / 4;
            object-fit: cover;
            object-position: 60% 50%;
            border-radius: app.$radius-lg;
            box-shadow: app.$shadow-lift;
        }

        .ring {
            position: absolute;
            width: 46%;
            top: -9%;
            left: -9%;
            z-index: 1;
            color: app.$color-accent;
            opacity: 0.9;

            @media (max-width: 520px) {
                top: -6%;
                left: -4%;
            }
        }

        &::after {
            content: "";
            position: absolute;
            right: -1.25rem;
            bottom: -1.25rem;
            width: 55%;
            height: 55%;
            border-radius: app.$radius-lg;
            background-color: app.$color-brand;
            opacity: 0.12;
            z-index: -1;

            @media (max-width: 520px) {
                right: -0.5rem;
                bottom: -0.75rem;
            }
        }

        isolation: isolate;
    }
</style>
