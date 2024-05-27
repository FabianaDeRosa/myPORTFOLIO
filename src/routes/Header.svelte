<script>
	import Nav from './Nav.svelte';
</script>

<section class="nav">
	<button><a href="/"> </a></button>
	<Nav />
</section>

<style lang="scss">
	.nav {
		display: grid;
		grid-template-rows: auto 1fr;
		padding: 2.4rem 2.4rem;

		button {
			background: none;
			cursor: pointer;
			border: none;
			text-align: left;
			width: 16rem;

			a {
				display: block;
				background-image: url('../lib/images/assets/fab.png');
				background-position: top;
				background-repeat: no-repeat;
				background-size: contain;
				height: 10rem;
				transform: translateY(-1rem);
			}
		}
	}

	@media screen and (max-width: 600px) {

        .nav{
			
            button{
                width: 30rem;
                a{
                    height: 13rem;
                }
            }
        }
}

</style>
