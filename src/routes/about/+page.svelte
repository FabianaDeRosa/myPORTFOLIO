<svelte:head>
    <title>About</title>
    <meta name="Portfolio works" content="A collection of my works">
</svelte:head>


<script>
	import Playground from "./Playground.svelte";
</script>



<div id="cv">
    <div id="p5">
        <Playground/>
    </div>
    <div class="logo"></div>
    <p>Hi! I'm <span>Fabiana De Rosa</span>, a junior creative developer born in Sorrento, Italy. My enthusiasm for both technology and art fueled my decision to pursue a degree in Interaction Design and Media Arts. This passion has not only shaped my academic journey but has also inspired me to embark on travels to explore diverse exhibitions and cultures around the world. I like to see each project as an opportunity to blend technical expertise with artistic expression, from sketching concepts to crafting unique digital experiences that captivate and inspire.</p>
    <a download="./assets/cv.png" href="./assets/cv.png"><button><i class="fa-solid fa-download"></i>CV</button></a>
    <div class="contacts">
        <i class="fa-brands fa-linkedin fa-xl"></i>
        <a href="https://www.linkedin.com/in/derosafabiana/" target="_blank">fabianaderosa</a>
        <i class="fa-solid fa-envelope fa-xl"></i>
        <a href="mailto:fabianadr00@gmail.com">fabianadr00@gmail.com</a>
    </div>
</div>


<style lang="scss">

    :global(main){
        display: grid;
    }

    #cv{
        align-self: center;
        display: grid;
        font-family: 'Mono',"DM Mono", monospace;
        justify-items: center;
        grid-template-columns:repeat(auto-fit, minmax(70ch, 1fr));
        margin-top: 4rem;
        margin-bottom: 2.5rem;

        .logo{
            display: none;
            width: 3rem;
            background-image: url('../../lib/images/icons/logo.png');
			background-position: center;
			background-repeat: no-repeat;
			background-size: contain;
			height: 3rem;
        }

        a {
            text-decoration: none;
            color: map-get($colors, black );
            button{
            border: 1px solid black;
            background-color: transparent;
            cursor: pointer;
            padding: 1rem;
            font-size: 1.1rem;
            font-family: 'Mono',"DM Mono", monospace;
            
            &:hover{
                background-color: black;
                color: white;
            }

            i{
                padding-right: .7em;
            }
        }
        }
        

        p{
            margin-bottom: 4rem;
            margin-top: 5rem;
            width: 65%;
            padding-bottom: 0;
            justify-self: center;
            text-align: center;
            

            span{
                color: map-get($colors, secondary );
                font-weight: 700;
            }

        }


    .contacts{
        justify-self: center;
        align-self: center;
        padding: 4.5rem;
        padding-bottom: 0;

        a{
            &:first-of-type{
                padding-right: 1em;
            }
        }
    }
    }


    @media screen and (max-width: 600px) {

        #cv{
            margin-top: 3rem;
            grid-template-columns:repeat(auto-fit, minmax(40ch, 1fr));

            .logo {
                display: block;
            }

           

            .contacts{
                display: flex;
                align-items: center;
                i{
                    padding-right: .5rem;
                }
            }

            #p5{
                display: none;
            }
        }

    }  
</style>