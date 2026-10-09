<script lang="ts">
    const alma = "https://secure.helloalma.com/providers/deandre-dyer/";

    const services = [
        {
            title: "School Services",
            text: "Our specialized school services offer tailored support and guidance to help students thrive both academically and emotionally, ensuring a holistic approach to education and mental well-being.",
            image: "/images/school.jpeg",
            alt: "A counselor taking notes while listening to a student",
            position: "50% 40%",
            href: "tel:346-386-7138",
            cta: "Call Now",
            external: false
        },
        {
            title: "Cognitive Behavioral Therapy",
            text: "Cognitive Behavioral Therapy empowers you to challenge negative thought patterns and behaviors, unlocking a path to a more positive and proactive mindset.",
            image: "/images/cbt.jpeg",
            alt: "A client talking with a therapist in a calm office",
            position: "50% 40%",
            href: alma,
            cta: "Cognitive Services",
            external: true
        },
        {
            title: "Child-Centered Play Therapy",
            text: "Child-Centered Play Therapy provides a safe and nurturing environment where children can express themselves and explore emotions through the power of play.",
            image: "/images/ccpt.png",
            alt: "A therapist and a child playing together on a rug",
            position: "50% 50%",
            href: alma,
            cta: "Child Services",
            external: true
        },
        {
            title: "Eye Movement Desensitization and Reprocessing",
            text: "Eye Movement Desensitization and Reprocessing harnesses the self-healing potential of your brain to process and overcome trauma-related memories and stress.",
            image: "/images/edmr.jpeg",
            alt: "A client following a therapist's finger with their eyes during EMDR",
            position: "30% 35%",
            href: alma,
            cta: "EMDR Services",
            external: true
        }
    ];
</script>

<section id="services" class="section">
    <div class="container">
        <div class="section-head">
            <span class="eyebrow">What we offer</span>
            <h2>Our Services</h2>
        </div>

        <div class="grid">
            { #each services as service }
                <article class="card">
                    <div class="media">
                        <img src={ service.image } alt={ service.alt } loading="lazy" style={ `object-position: ${ service.position };` }>
                    </div>
                    <div class="body">
                        <h3>{ service.title }</h3>
                        <p>{ service.text }</p>
                        <a href={ service.href } target={ service.external ? "_blank" : undefined } rel={ service.external ? "noopener" : undefined } class="link">
                            { service.cta }
                            <svg viewBox="0 0 20 20" aria-hidden="true"><path d="M4 10h11m-4-4 4 4-4 4" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/></svg>
                        </a>
                    </div>
                </article>
            { /each }
        </div>
    </div>
</section>

<style lang="scss">
    @use "$lib/scss/variables" as app;

    .grid {
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        gap: 2rem;

        @media (max-width: 760px) {
            grid-template-columns: 1fr;
            gap: 1.5rem;
        }
    }

    .card {
        display: flex;
        flex-direction: column;
        overflow: hidden;
        border-radius: app.$radius-md;
        background-color: app.$color-background;
        border: 1px solid app.$color-shade;
        transition: transform 220ms ease, box-shadow 220ms ease, border-color 220ms ease;

        &:hover {
            transform: translateY(-4px);
            box-shadow: app.$shadow-lift;
            border-color: transparent;

            img { transform: scale(1.03); }
        }
    }

    .media {
        overflow: hidden;
        aspect-ratio: 16 / 10;
        background-color: app.$color-elevate;

        img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 500ms ease;
        }
    }

    .body {
        flex: 1;
        display: flex;
        flex-direction: column;
        gap: 0.75rem;
        padding: 1.75rem 1.75rem 2rem;

        h3 {
            font-size: 1.5rem;
        }

        p {
            flex: 1;
        }
    }

    .link {
        display: inline-flex;
        align-items: center;
        gap: 0.4rem;
        margin-top: 0.5rem;
        width: max-content;

        font-weight: app.$weight-bold;
        color: app.$color-brand;

        svg {
            width: 1.1rem;
            height: 1.1rem;
            transition: transform 180ms ease;
        }

        &:hover {
            color: app.$color-brand-deep;
            svg { transform: translateX(3px); }
        }
    }
</style>
