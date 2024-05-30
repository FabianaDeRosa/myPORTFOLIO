<script>
    export let title = "Coming soon";
    export let img_2;
    export let sub;
    export let descr;
    export let tools;
    export let video;
    export let link;
    export let link_2;
</script>



<div id="single-item-wrapper">
    <section id="single-item">
        <article>
            <h2>{title}</h2>
            <h3>{sub}</h3>
            <p>{descr}</p>
            {#if link_2}
            <a href="{link_2}" target="_blank">{title} case study</a>
             {/if}
            <div>
                {#each tools as tool}
                    <img src="{tool}" alt={title} />
               {/each}
            </div>
           {#if link}
           <iframe src={link} title="{title}" allowfullscreen></iframe>
          {/if}
            
        </article>
    </section>
    
    <section id="single-item-2">
        <article>
            {#each img_2 as image}
                <img src="{image}" alt={title} />
            {/each}
        </article>
        <article>
            {#each video as vid}
            <video autoplay loop muted playsinline controls class="video"> 
                <source src={vid} type="video/mp4">
                    Your browser does not support the video tag.
            </video>
            {/each}
        </article>
    </section>
</div>



<style lang="scss">

#single-item-wrapper{
    display: grid;
    grid-template-rows: auto auto;
   // gap: 7rem;


    #single-item{
        padding-bottom: 3rem;
        article{
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(70ch, 1fr));
        justify-items: center;
            h2{
                font-weight: 700;
                font-family: 'CactusJack';
                font-size: 5rem;
            }
            h3{
                font-weight: 300;
                font-size: 1rem;
                text-align: center;
                 width: 60%;
                color: #bdbdbd;
            }
            p{
                font-weight: 300;
                font-size: 1rem;
                text-align: center;
                width: 60%;
                color: #bdbdbd;
                padding-bottom: 1.1rem;
                margin-top: 0;

                a{
                    color: map-get($colors, secondary );
                }
            }

            a{
                font-weight: 200;
                color: map-get($colors, secondary );
                padding-bottom: 2rem;
            }

            div{
                padding-bottom: 7rem;
                img{
                height: 2.5em;
                padding-right: 1rem;
            }
            }
            
            iframe{
                padding: 0;
                width: 70% ;
                height: 381px;
                border: none; 
                margin: 0;
                
            }
              
            }
            
    }

    #single-item-2{
        article{
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(60ch, 1fr));
            place-items: center;
            gap: 3rem;
          
            img{
                width: 30rem;
            }

            .video{
                width: 30rem;
                justify-self: center;
            }
        }
    }

}
@media screen and (max-width: 600px) {

    #single-item-wrapper{
        grid-template-rows: 1fr ;

        #single-item{
            article{
                grid-template-columns: 35rem;
                h2{
                font-size: 6.8rem;
                width: 70%;
                line-height: 5rem;
                margin-bottom: 1.4rem;
                text-align: center;
                font-weight: 700;
                font-family: 'CactusJack';
            }
            h3{
                font-size: 1.5rem;
              
            }
            p{
                font-size: 1.5rem;
                width: 80%;
            }

            div{
                img{
                height: 3rem;
            }
            }

            iframe{
                padding: 0;
                width: 80% ;
                height: 252px;
            }
          
        }
    }

        #single-item-2{
        article{
            grid-template-columns: 35rem;
        }
    }
    }
}
</style>