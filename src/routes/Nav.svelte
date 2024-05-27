<script>
	import works from '$lib/JSON/works.json';
	let dim;
	$: innerWidth = dim;
	$: condition = innerWidth < 600;
</script>

<svelte:window bind:innerWidth={dim} />

<div id="nav">
	<div class="title">
		<a href="/">works</a>
	</div>
	<div class="nav-links">
		{#each works as work}
			<a href="/{work.id - 1}" target="_self">{work.title} </a>
		{/each}
	</div>
	<div class="title">
		<a href="/about">about</a>
	</div>
	<div class="title">
		<a href="/skills">skills</a>
	</div>
</div>
{#if condition}
	<div id="title2-wrap">
		<div class="title2">
			<a href="/about">about</a>
		</div>
		<div class="title2">
			<a href="/skills">skills</a>
		</div>
	</div>
{/if}

<style lang="scss">
	#nav {
		display: grid;
		align-self: start;
		padding: 0 1rem;

		.title {
			padding: 0;
			padding-bottom: 0.7rem;
			&:first-child,
			&:nth-child(3) {
				padding-top: 1.3rem;
			}
			a {
				text-transform: uppercase;
				color: map-get($colors, black);
				font-weight: 700;
				margin: 0;
				font-family: CactusJack;
				font-size: 2rem;
				text-decoration: none;
				&:hover {
					color: map-get($colors, black);
				}
			}
		}
		.nav-links {
			display: grid;
			grid-auto-flow: row;
			padding: 0;
			a {
				padding: 0.1rem;
				text-decoration: none;
				color: #d8d8d8;
				font-weight: 300;

				&:hover {
					color: map-get($colors, secondary);
					text-decoration: underline;
				}
			}
		}
	}
	#title2-wrap {
		display: grid;
		grid-template-columns: 1fr 1fr;
		margin-top: 3rem;
		.title2 {
			padding: 0;
			padding-bottom: 0.4rem;
			justify-self: center;

			a {
				text-transform: uppercase;
				color: map-get($colors, black);
				font-weight: 700;
				margin: 0;
				font-family: 'CactusJack';
				font-size: 3rem;
				text-decoration: none;
				&:hover {
					color: map-get($colors, black);
				}
			}
		}
	}

	@media screen and (max-width: 600px) {
		#nav {
			display: none;
		}
		#title2-wrap {
			.title2 {
				a {
					font-weight: 700;
					font-family: 'CactusJack';
				}
			}
		}
	}
</style>
