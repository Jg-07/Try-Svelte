<script>
	import anime from "animejs";
	import { onMount } from "svelte";
	// logic
	export let textProp = "Animation!";
	const text = textProp.split("");

	onMount(() => {
		anime({
			targets: ".animatable-text",
			delay: anime.stagger(50),
			translateY: [100, 0],
			duration: 1000,
		});
	});
</script>

<h1 class="animatable">
	{#each text as letter}
		<span class="animatable-text">{letter}</span>
	{/each}
</h1>

<style>
	.animatable {
		font-weight: 400;
		display: flex;
	}
	.animatable-text {
		display: block;
	}
</style>
