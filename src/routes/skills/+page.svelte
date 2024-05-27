<script>
	import { fade } from 'svelte/transition';
	let isOpen = false;

	function toggleAnimation() {
		isOpen = !isOpen;
	}
	let imgUrls = [
		'./assets/tools_logos/touchdesigner.png',
		'./assets/tools_logos/ableton.png',
		'./assets/tools_logos/figma.png',
		'./assets/tools_logos/arduino.png',
		'./assets/tools_logos/visual-studio.png',
		'./assets/tools_logos/svelte.svg.png',
		'./assets/tools_logos/p5.png',
		'./assets/tools_logos/html.svg.png',
		'./assets/tools_logos/sass.svg.png',
		'./assets/tools_logos/js.svg.png',
		'./assets/tools_logos/illustrator.png',
		'./assets/tools_logos/photoshop.png',
		'./assets/tools_logos/indesign.png',
		'./assets/tools_logos/lightroom.png',
		'./assets/tools_logos/after-effect.png',
		'./assets/tools_logos/xd.png',
		'./assets/tools_logos/maya.png',
		'./assets/tools_logos/processing.png',
		'./assets/tools_logos/spline.png',
		'./assets/tools_logos/canva.png',
		'./assets/tools_logos/unreal.png',
		'./assets/tools_logos/wwise.png'
	];
</script>

<svelte:head>
	<title>Skills</title>
	<meta name="Portfolio works" content="A collection of my works" />
</svelte:head>

<div id="skills">
	<div
		class="folder"
		on:click={toggleAnimation}
		class:open={isOpen}
		role="button"
		aria-pressed={isOpen}
		tabindex="0"
		on:keydown={(event) => {
			if (event.key === 'Enter' || event.key === ' ') toggleAnimation();
		}}
	>
		<div class="back" />
		<div class="cover" />
		<div class="paper" />
		<h2>SKILLS</h2>
	</div>
	{#if isOpen}
		<div class="grid" transition:fade={{ delay: 250, duration: 500 }}>
			{#each imgUrls as immagini}
				<div class="img">
					<img src={immagini} alt="" />
				</div>
			{/each}
		</div>
	{/if}
</div>

<style lang="scss">
	#skills {
		display: grid;
		grid-template-rows: min-content auto;

		/*.folder{
        background-image: url('../../lib/images/assets/folder-mac.png');
        background-position: center;
        background-repeat: no-repeat;
        background-size: contain;
        height: 3.5rem;
        margin-top: 5rem;
    }*/

		.grid {
			display: grid;
			grid-template-columns: min-content min-content min-content min-content min-content;
			gap: 5rem;
			justify-self: center;
			animation: 3s linear 1s slidein;
		}

		img {
			width: 3rem;
		}
	}

	.folder {
		perspective: 2500px;
		margin: 100px auto;
		width: 320px;
		text-align: center;
		cursor: pointer;
		h2 {
			font-family: 'CactusJack';
			margin: 0;
			font-size: 2.3rem;
			font-weight: 200;
		}
	}
	.folder:before {
		content: '';
		position: absolute;
		bottom: 76.33px;
		left: 0;
		right: 0;
		margin: 0 6em;
	}
	.folder:after {
		content: '';
		position: absolute;
		bottom: -2px;
		left: 0;
		right: 0;
		margin: 0 5.33em;
	}
	.folder .back {
		width: 166.67px;
		height: 106.67px;
		border-radius: 10px 0 10px 10px;
		position: relative;
		margin: 0 auto;
		background: #7aa8e0;
	}
	.folder .cover {
		width: 166.67px;
		height: 106.67px;
		border-radius: 10px 10px 10px 10px;
		position: absolute;
		top: 0;
		left: 0;
		right: 0;
		z-index: 5;
		margin: 0 auto;
		background: #82b3f0;
		transform-origin: 0 108%;
		transition: transform 1.25s ease;
	}
	.folder .back:after {
		position: absolute;
		content: '';
		width: 60px;
		height: 14px;
		border-radius: 6px 6px 0 0;
		background: #7aa8e0;
		top: -11px;
		right: 0;
		border: 0;
	}
	.paper {
		background: #fff;
		height: 33.33px;
		position: absolute;
		top: 6px;
		left: 0;
		right: 0;
		bottom: 0;
		margin: 0 86.67px;
		opacity: 0;
		transform: translateY(33.33px);
		transition: transform 0.75s ease, opacity 0.75s ease;
	}
	.folder.open .cover {
		transform: rotateX(-30deg);
	}
	.folder.open .paper {
		transform: translateY(0px);
		opacity: 1;
	}

	@media screen and (max-width: 600px) {
		#skills {
			grid-template-rows: min-content min-content;
			height: 180vh;
			width: 100%;
			margin: 0 auto;
			.grid {
				grid-template-columns: min-content min-content min-content;
				gap: 4rem;
				img {
					width: 4rem;
				}

				.folder {
					h2 {
						font-family: 'CactusJack';
						font-weight: 200;
					}
				}
			}
		}
	}
</style>
