<style lang="scss">
    @use "$lib/scss/variables" as app;

main {
    width: 100vw;
    margin-top: 10rem;
    padding-bottom: 5rem;
    
    section#prices {
        display: flex;
        flex-direction:row;
        justify-content: space-around;
        gap: 3rem;
        padding: 3rem;

        @media screen and (max-width: 1437px) {
            flex-direction: column;
            align-items: center;
        }

        div.card {

            width: 23rem;
            height: 30rem;
            border-top-left-radius: 1rem;
            border-top-right-radius: 1rem;

            display: flex;
            flex-direction: column;
            align-items: center;

            gap: 3rem;

            box-shadow: 0px 0px 2px 0px;

            span {
                
                &:nth-of-type(1) {
                display: block;
                width: 100%;
                height: .5rem;
                border-top-left-radius: 1rem;
                border-top-right-radius: 1rem;
                }

                &:nth-of-type(2){
                    font-weight: bolder;
                    font-size: 3rem;
                }

            }

            .descriptor {
                display: flex;
                flex-direction: column;
                justify-content: center;

                text-align: center;

                h1 {
                    font-size: 1.7rem;

                    margin-bottom: 1rem;
                }

                p {
                    font-weight: 280;
                }
            }

            
        }

    }
}

</style>

<main>
    <h1 style="align-self: center;"> Our Prices</h1>
    <section id="prices">
        
        <div class="card">
            <span style="background-color: royalblue;"></span>

            <div class="descriptor">
                <h1>Sliding Scale Therapy</h1>
                <p>Sliding Scale Pricing offers a flexible payment system to ensure our services are accessible to all, adjusting the cost based on your individual financial circumstances.</p>
            </div>
            
            <span>$100-120</span>

            <a href="https://secure.helloalma.com/providers/deandre-dyer/"  target="_blank"     class="button" style="background-color: royalblue; color:white; font-size: 1.5rem; padding:1rem"> Book Now</a>
        </div>

        <div class="card">
            <span style="background-color: orange;"></span>

            <div class="descriptor">
                <h1>EDMR Intensive</h1>
                <p>Our EMDR Intensive program provides concentrated and tailored sessions designed for profound healing, allowing for significant progress in a shorter period of time.</p>
            </div>

            <span>$175</span>
            <a href="https://secure.helloalma.com/providers/deandre-dyer/"  target="_blank" class="button" style="background-color: orange; color:white; font-size: 1.5rem; padding:1rem"> Book Now</a>

        </div>

        <div class="card">
            <span style="background-color: yellowgreen;"></span>

            <div class="descriptor">
                <h1>Play/Talk Therapy</h1>
                <p>Our Play/Talk Therapy service merges the expressive power of play with the insights of traditional talk therapy, facilitating children's communication and emotional growth in a language they understand best.</p>
            </div>
           
            <span>$150</span>
            <a href="https://secure.helloalma.com/providers/deandre-dyer/"  target="_blank" class="button" style="background-color: yellowgreen; color:white; font-size: 1.5rem; padding:1rem"> Book Now</a>
        </div>

        <div class="card">
            <span style="background-color: red;"></span>
            <div class="descriptor">
                <h1>In Network Insurance</h1>
                <p>Our In-Network Insurance option allows you to receive therapy with the convenience and affordability provided by our partnerships with major insurance providers.</p>
            </div>
            
            <span style="font-size: 2rem;">Typically $30-$40</span>
            <a href="https://secure.helloalma.com/check-my-insurance-coverage/?provider=deandre-dyer/" target="_blank"    class="button" style="background-color: red; color:white; font-size: 1.5rem; padding:1rem"> Coverage</a>

        </div>
    </section>
</main>