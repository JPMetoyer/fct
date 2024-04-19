<style lang="scss">
    @use "$lib/scss/variables" as app;

    main {
        margin-top: 8rem;
        width: 100vw;

        display: flex;
        overflow: hidden;

        section#services {

            width: 90%;
            display: flex;
            flex-direction: row;
            justify-content: space-around;

            margin: 0 auto;


            @media screen and (max-width:1044px) {
                flex-direction: column;
                gap:5rem;
                align-items: center;

            }
            div.offer {

                display: flex;
                flex-direction: column;
                align-items: center;

                width: 30rem;
                padding: 3rem;

                

                div.graphic {

                    img {
                        border-radius: 50%;
                        width: 18rem;
                        height: 18rem;
                        border: 3px solid app.$color-brand;
                    }
                }

                div.content {
                    text-align: center;
                    display: flex;
                    flex-direction: column;
                    align-items: center;
                    gap:1rem;

                    h1 {
                        font-weight: lighter;
                    }

                    a {
                        font-size: 1.3rem;
                        color: white;
                    }
                }

            }
    }
    }
    


</style>

<main>
<h1 style="align-self: center;">Our Services</h1>

    <section id="services">

        
        <div class="offer">
            <div class="graphic">
                <img src="/images/cbt.jpeg" alt="">
            </div>

            <div class="content">
                <h1>Cognitive Behavioral Therapy</h1>
                <p>Cognitive Behavioral Therapy empowers you to challenge negative thought patterns and behaviors, unlocking a path to a more positive and proactive mindset.</p>
                <a href="https://secure.helloalma.com/providers/deandre-dyer/"  target="_blank" class="button">Cognitive Services </a>

            </div>
        </div>
        
        <div class="offer">
            <div class="graphic">
                <img src="/images/ccpt.png" alt="">
            </div>

            <div class="content">
                <h1>Child-Centered Play Therapy</h1>
                <p>Child-Centered Play Therapy provides a safe and nurturing environment where children can express themselves and explore emotions through the power of play.</p>
                <a href="https://secure.helloalma.com/providers/deandre-dyer/"  target="_blank" class="button"> Child Services</a>
            </div>
        </div>

        <div class="offer">
            <div class="graphic">
                <img src="/images/edmr.jpeg" alt="">
            </div>

            <div class="content">
                <h1 style="line-height: 100%;">Eye Movement Desensitization and Reprocessing</h1>
                <p>Eye Movement Desensitization and Reprocessing harnesses the self-healing potential of your brain to process and overcome trauma-related memories and stress.</p>
                <a href="https://secure.helloalma.com/providers/deandre-dyer/"  target="_blank" class="button">EMDR Services</a>
            </div>
        </div>


    </section>

</main>
