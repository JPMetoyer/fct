<script lang="ts">
    const year = new Date().getFullYear();
</script>

<footer>
    <div class="container">
        <div class="top">
            <a href="/" class="brand">
                <img src="/icons/fctherapy.jpg" alt="" width="69" height="48">
                <span>Full Circle Therapy</span>
            </a>

            <a href="https://secure.helloalma.com/providers/deandre-dyer/" target="_blank" rel="noopener" class="button">Book an appointment</a>
        </div>

        <div class="details">
            <div>
                <h4>Location</h4>
                <p>350 Nursery Road<br>Spring TX</p>
            </div>

            <div>
                <h4>Contact</h4>
                <p>
                    Deandre A. Dyer, LCSW<br>
                    <a href="tel:346-386-7138">346-386-7138</a><br>
                    <a href="mailto:Deandre.Dyer@yahoo.com">Deandre.Dyer@yahoo.com</a>
                </p>
            </div>

            <div>
                <h4>Specialties</h4>
                <p><a href="https://secure.helloalma.com/providers/deandre-dyer/" target="_blank" rel="noopener">Psychotherapist; EMDR, Play Therapy, TF-CBT</a></p>
            </div>
        </div>

        <div class="legal">
            <p>&copy; { year } Full Circle Therapy PLLC. All rights reserved.</p>
        </div>
    </div>
</footer>

<style lang="scss">
    @use "$lib/scss/variables" as app;

    footer {
        background-color: app.$color-brand-deep;
        color: rgba(255, 255, 255, 0.78);
        padding: 4.5rem 0 2rem;
    }

    .top {
        display: flex;
        align-items: center;
        justify-content: space-between;
        flex-wrap: wrap;
        gap: 1.5rem;
        padding-bottom: 2.5rem;
        border-bottom: 1px solid rgba(255, 255, 255, 0.12);

        .button {
            background-color: app.$color-accent;
            color: app.$color-brand-deep;

            &:hover {
                background-color: #FFFFFF;
                box-shadow: none;
            }
        }
    }

    .brand {
        display: flex;
        align-items: center;
        gap: 0.85rem;

        img {
            width: 4.3rem;
            height: 3rem;
            object-fit: cover;
            border-radius: 0.8rem;
            box-shadow: 0 0 0 1px rgba(255, 255, 255, 0.15);
        }

        span {
            font-family: app.$typeface-heading;
            font-size: 1.4rem;
            font-weight: app.$weight-semibold;
            color: #FFFFFF;
        }
    }

    .details {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 2rem;
        padding: 2.5rem 0;

        @media (max-width: 720px) {
            grid-template-columns: 1fr;
            gap: 1.75rem;
        }

        h4 {
            margin-bottom: 0.6rem;
            font-size: 0.75rem;
            letter-spacing: 0.12em;
            text-transform: uppercase;
            color: app.$color-accent;
        }

        p {
            color: rgba(255, 255, 255, 0.82);
            line-height: 1.8;
        }

        a {
            border-bottom: 1px solid rgba(255, 255, 255, 0.25);
            transition: border-color 160ms ease, color 160ms ease;
            overflow-wrap: anywhere;

            &:hover {
                color: #FFFFFF;
                border-bottom-color: app.$color-accent;
            }
        }
    }

    .legal {
        padding-top: 1.5rem;
        border-top: 1px solid rgba(255, 255, 255, 0.12);

        p {
            font-size: 0.85rem;
            color: rgba(255, 255, 255, 0.55);
        }
    }
</style>
