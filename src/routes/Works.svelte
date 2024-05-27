<script>
	export let id;
	export let title;
	export let img;
</script>

<article>
	<a href="/{id - 1}" style="background-image: url('{img}')">
		<span>{title}</span>
	</a>
</article>

<style lang="scss">
	article {
		a {
			display: block;
			background-position: center;
			background-repeat: no-repeat;
			background-size: cover;
			height: 20rem;
			text-decoration: none;
			color: black;
			text-transform: uppercase;
			font-size: 4rem;
			//font-weight: 700;
			position: relative;
			font-family: CactusJack;

			&:hover {
				cursor: pointer;
				box-shadow: inset 0 0 0 1000px rgba(255, 255, 255, 0.8);

				span {
					opacity: 100%;
					transition: opacity 0.3s ease-in-out;
				}
			}

			span {
				opacity: 0;
				position: absolute;
				top: 50%;
				left: 50%;
				transform: translate(-50%, -50%);
				text-align: center;
			}
		}
	}

	@media screen and (max-width: 600px) {
		article {
			a {
				height: 35rem;
				font-size: 7.5rem;
			}
		}
	}
</style>
