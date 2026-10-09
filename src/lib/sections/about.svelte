<section id="about" class="section">
    <div class="container grid">
        <div class="panel">
            <img src="/icons/fctherapy.jpg" alt="Full Circle Therapy PLLC logo" width="1685" height="1180">
        </div>

        <div class="content">
            <span class="eyebrow">About Us</span>
            <h2>Empowering Personal Growth Through Compassionate Therapy</h2>
            <p>As a dedicated clinician, Deandre Dyer LCSW brings a rich tapestry of experience from working with kids in schools to supporting adults with trauma. A proud alumnus of Texas State University and the University of Texas at Arlington, Deandre is well-equipped to connect with and support clients across all stages of life. Outside the office, he finds joy in fishing and making memories with his beloved puppies.</p>

            <ul class="tags" aria-label="Specialties">
                <li>EMDR</li>
                <li>Play Therapy</li>
                <li>TF-CBT</li>
            </ul>

            <a href="https://secure.helloalma.com/providers/deandre-dyer/" target="_blank" rel="noopener" class="button outline">More About Us</a>
        </div>
    </div>
</section>

<style lang="scss">
    @use "$lib/scss/variables" as app;

    #about {
        background-color: app.$color-elevate;
    }

    .grid {
        display: grid;
        grid-template-columns: 0.9fr 1.1fr;
        align-items: center;
        gap: 5rem;

        @media (max-width: 900px) {
            grid-template-columns: 1fr;
            gap: 2.5rem;
        }
    }

    .panel {
        position: relative;
        overflow: hidden;
        border-radius: app.$radius-lg;
        background-color: #1F75BD;
        box-shadow: app.$shadow-lift;

        img {
            width: 100%;
            aspect-ratio: 1685 / 1180;
            object-fit: cover;
        }

        @media (max-width: 900px) {
            max-width: 32rem;
        }
    }

    h2 {
        font-size: clamp(1.9rem, 3.6vw, 2.6rem);
        margin-bottom: 1.25rem;
    }

    p {
        font-size: 1.075rem;
        line-height: 1.75;
    }

    .tags {
        list-style: none;
        display: flex;
        flex-wrap: wrap;
        gap: 0.5rem;
        margin: 1.75rem 0 2rem;

        li {
            padding: 0.35rem 0.9rem;
            border-radius: 999px;
            background-color: app.$color-background;
            border: 1px solid app.$color-shade;
            font-size: 0.85rem;
            font-weight: app.$weight-semibold;
            color: app.$color-brand-deep;
        }
    }
</style>
