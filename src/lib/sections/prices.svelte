<script lang="ts">
    const alma = "https://secure.helloalma.com/providers/deandre-dyer/";

    const plans = [
        {
            title: "Sliding Scale Therapy",
            text: "Sliding Scale Pricing offers a flexible payment system to ensure our services are accessible to all, adjusting the cost based on your individual financial circumstances.",
            price: "$100–120",
            href: alma,
            cta: "Book Now",
            tone: "blue"
        },
        {
            title: "EMDR Intensive",
            text: "Our EMDR Intensive program provides concentrated and tailored sessions designed for profound healing, allowing for significant progress in a shorter period of time.",
            price: "$175",
            href: alma,
            cta: "Book Now",
            tone: "gold"
        },
        {
            title: "Play/Talk Therapy",
            text: "Our Play/Talk Therapy service merges the expressive power of play with the insights of traditional talk therapy, facilitating children's communication and emotional growth in a language they understand best.",
            price: "$150",
            href: alma,
            cta: "Book Now",
            tone: "green"
        },
        {
            title: "In Network Insurance",
            text: "Our In-Network Insurance option allows you to receive therapy with the convenience and affordability provided by our partnerships with major insurance providers.",
            label: "Copay",
            price: "Depends on individual plans",
            href: "https://secure.helloalma.com/check-my-insurance-coverage/?provider=deandre-dyer/",
            cta: "Check Coverage",
            tone: "deep"
        }
    ];
</script>

<section id="prices" class="section">
    <div class="container">
        <div class="section-head">
            <span class="eyebrow">Pricing</span>
            <h2>Our Prices</h2>
        </div>

        <div class="grid">
            { #each plans as plan }
                <article class="card { plan.tone }">
                    <h3>{ plan.title }</h3>
                    <p>{ plan.text }</p>

                    <div class="price" class:text={ plan.label }>
                        { #if plan.label }<span class="label">{ plan.label }</span>{ /if }
                        <span class="amount">{ plan.price }</span>
                    </div>

                    <a href={ plan.href } target="_blank" rel="noopener" class="button">{ plan.cta }</a>
                </article>
            { /each }
        </div>
    </div>
</section>

<style lang="scss">
    @use "$lib/scss/variables" as app;

    #prices {
        background-color: app.$color-elevate;
    }

    .grid {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        gap: 1.25rem;

        @media (max-width: 1080px) {
            grid-template-columns: repeat(2, 1fr);
        }

        @media (max-width: 600px) {
            grid-template-columns: 1fr;
        }
    }

    .card {
        --tone: #{ app.$color-brand };

        &.gold { --tone: #{ app.$color-gold }; }
        &.green { --tone: #{ app.$color-accent-deep }; }
        &.deep { --tone: #{ app.$color-brand-deep }; }

        position: relative;
        display: flex;
        flex-direction: column;
        gap: 1rem;
        padding: 2.25rem 1.75rem 1.75rem;
        overflow: hidden;

        border-radius: app.$radius-md;
        background-color: app.$color-background;
        box-shadow: app.$shadow-soft;
        transition: transform 220ms ease, box-shadow 220ms ease;

        &::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 5px;
            background-color: var(--tone);
        }

        &:hover {
            transform: translateY(-4px);
            box-shadow: app.$shadow-lift;
        }

        h3 {
            font-size: 1.4rem;
        }

        p {
            flex: 1;
            font-size: 0.95rem;
        }

        .button {
            width: 100%;
            background-color: var(--tone);

            &:hover {
                filter: brightness(0.9);
                box-shadow: none;
            }
        }
    }

    .price {
        display: flex;
        flex-direction: column;
        gap: 0.15rem;
        padding: 1.25rem 0 0.5rem;
        border-top: 1px solid app.$color-shade;

        .label {
            font-size: 0.75rem;
            font-weight: app.$weight-bold;
            letter-spacing: 0.1em;
            text-transform: uppercase;
            color: app.$color-midground;
        }

        .amount {
            font-family: app.$typeface-heading;
            font-size: 2.5rem;
            font-weight: app.$weight-semibold;
            line-height: 1.1;
            color: app.$color-foreground;
        }

        &.text .amount {
            font-size: 1.35rem;
            line-height: 1.25;
        }
    }
</style>
