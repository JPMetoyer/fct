


<style lang="scss">
    @use "$lib/scss/variables" as app;


    footer {
        background-color: app.$color-shade;
        padding: 2rem 4vw 5rem 4vw;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        gap: 1rem;
        height: 10rem;

        a {

            h1 {
                color: app.$color-brand;
                margin-left: 1rem;
            }
        }

        #logo {
            height: 2.8rem;
            fill: app.$color-brand;
            stroke: transparent;
            display: flex;
            align-items: center;
            justify-content: flex-start;
        }

        #logo img {
            max-height: 100%;
            max-width: 100%;
        }

        #trail {
            margin: 0rem 0px;
            display: flex;
            justify-content: space-between;
        }

        #trail p {
            color: app;
            font-size: .8rem;
            padding-bottom: 1rem;
        }
       
    }

    #documentation {
        border-bottom: 1px dashed black;
        transition: all 1s ease-in;

        :hover {
            border-bottom: 1px dashed red;
        }
    }



</style>


<footer>
    <a href="/" id="logo">
        <img src="/icons/fctherapy.jpg" alt="">
        <h1 style="
        text-decoration: none;
        font-weight: 700;
        font-size: 120%;">Full Circle Therapy</h1>
    </a>
    
    <div id="trail">
        <p>350 Nursery Road Spring TX</p>
        <p><span style="text-decoration: underline;"> Deandre A. Dyer, LCSW | 346-386-7138 | Deandre.Dyer@yahoo.com </span> | <a id="documentation" href="https://secure.helloalma.com/providers/deandre-dyer/" target="_blank"> <i>Psychotherapist; EMDR, Play Therapy, TF-CBT</i></a>


        </p>
    </div>
</footer>




