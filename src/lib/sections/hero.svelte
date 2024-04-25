<style lang="scss">
    @use "$lib/scss/variables" as app;


    main {

        width: 100vw;
        overflow: hidden;


        section#hero {
    width: 100%;
    height: 40rem;
    background-color: red;

    background: url("/images/landingimage.jpeg") no-repeat center;
    background-size: cover;

    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;

    position: relative;

    @media screen and (max-width:519px) {
        justify-content: center;
        align-items: center;
    }

    div#promotion {
        width: 50%; 
        height: 50%;

        background-color: rgba(187, 255, 0, 0.5);
        border-top-left-radius: 50% 100%; 
        border-top-right-radius: 50% 100%; 
        position: absolute;
        top: 50%; 
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        text-align: center;
        overflow: hidden;

        @media screen and (max-width:995px) {
            width: 60%;
        }

        @media screen and (max-width:738px) {
            width: 30rem;
        }

        @media screen and (max-width: 521px) {
            width: 70%;
            height: 60%;
            position: relative;
            top: 5%;
            border-radius: 50%;
           
            h1 {
                font-size: 20px;
                margin-top: 0;
                
            }

           
        }



       

        h1 {
            color: black;
            font-weight:300;

            span {
                font-weight: 550;
            }

            &:nth-child(1) {
                margin-top: 2rem;

            }
        } 

        p {
            margin-top: 1.3rem;
            margin-bottom: 1.3rem;
            font-weight: 400;
        }

        a {
            margin-top: 8px;
            color: white;
            background-color: app.$color-brand;
            font-size: 20px;

        }

    }
}

    }


</style>
<main>

    
    <section id="hero">
        <div id="promotion">
            <h1 id="first">Your Journey <span>Today</span></h1>
            <h1>Your Triump <span>Tomorrow</span></h1>
            <p>

                Counseling & Trauma Services 
                <br>
                
                Consulting & School Services 
            </p>
            <a href="https://secure.helloalma.com/providers/deandre-dyer/"  target="_blank" class="button"> Book an appointment</a>
        </div>

    </section>
</main>
