<script>
	import anime from 'animejs'
	import { onMount } from 'svelte'

	export let animate = 'NONE'
	export let type = 'h1'
	export let text = ''

	export let loop = false
	export let durationLine = 1000
	export let delay = 2000

	let element = null
	let line = null

	$: {
		if (animate == 'ANIMATE') {
			anime.timeline({ loop: loop }).add({
				targets: line,
				scaleX: [0, 1],
				opacity: [0.5, 1],
				easing: 'easeInOutExpo',
				duration: durationLine,
				delay: delay,
			})
		} else if (animate == 'REVERT') {
			anime.timeline().add({
				targets: line,
				scaleX: 0,
				opacity: 0,
				easing: 'easeInOutExpo',
				duration: 0,
			})
		}
	}
</script>

<svelte:element
	this={type}
	bind:this={element}
	class={$$props.class}
	{...$$restProps}
>
	<span
		class="relative inline-block pt-[0.1rem] pr-[0.05rem] pb-[0.15rem] text-wrapper"
	>
		<span class="letters">
			{text}
		</span>
		<span
			bind:this={line}
			class="absolute opacity-0 p-[2px] left-0 height-[2px] w-full bg-white -bottom-2 origin-[100%_100%] line"
		></span>
	</span>
</svelte:element>
