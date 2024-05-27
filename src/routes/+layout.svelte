<script>
	import '../app.scss';	
	import Header from "./Header.svelte";
	
</script>




<div id="wrapper">
	<Header />

	<main>
	  <slot />
	</main>

	<p>Developed by Fabiana De Rosa</p>
	
</div>
  


<style lang="scss">

	#wrapper {
		display: grid;
		grid-template-columns: auto 1fr;
		height: 100vh;
		padding: 0;
		width: 100%; 
		max-width: 1300px; 
		margin: 0 auto;

		p{	
			grid-column: 1 / 3;
			color: lightgray;
			justify-self: center;
			font-weight: 100;
			padding-top: .7rem;
			padding-bottom: .4rem;
			font-size: .7rem;
		}
		
	
	}

	@media screen and (max-width: 600px) {

		#wrapper {
			grid-template-columns: 1fr; 
			

		  p{	
			text-align: center;
			grid-column: 1;
		}
	}
}
</style>