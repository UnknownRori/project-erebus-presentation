<script>
	import anime from 'animejs'
	import {onMount} from 'svelte'

	export let animate = 'NONE'
	export let type = 'h1'
	export let text = ''

	export let loop = false
	export let durationLine = 1000
	export let durationLetters = 400

	let element = null
	let textWrapper = null
	let line = null
	let letterNodes = null

	onMount(() => {
		textWrapper = element.querySelector('.letters')
		line = element.querySelector('.line')
		textWrapper.innerHTML = textWrapper.textContent.replace(
			/\S/g,
			"<span class='letter'>$&</span>"
		)
		letterNodes = textWrapper.querySelectorAll('.letter')
	})

	$: {
		if (animate == 'ANIMATE') {
			anime
				.timeline({loop: loop})
				.add({
					targets: line,
					scaleX: [0, 1],
					opacity: [0.5, 1],
					easing: 'easeInOutExpo',
					duration: durationLine,
				})
				.add({
					targets: letterNodes,
					opacity: [0, 1],
					translateX: [40, 0],
					translateZ: 0,
					scaleX: [0.3, 1],
					easing: 'easeOutExpo',
					duration: durationLetters,
					offset: '-=600',
					delay: (el, i) => 150 + 25 * i,
				})
		} else if (animate == 'REVERT') {
			anime
				.timeline()
				.add({
					targets: line,
					scaleX: 0,
					opacity: 0,
					easing: 'easeInOutExpo',
					duration: 0,
				})
				.add({
					targets: letterNodes,
					opacity: 0,
					translateX: 0,
					translateZ: 0,
					scaleX: 0,
					easing: 'easeOutExpo',
					duration: 0,
					offset: '-=600',
				})
		}
	}
</script>

<svelte:element this={type} bind:this={element} class={$$props.class} {...$$restProps}>
	<span class="relative inline-block pt-[0.1rem] pr-[0.05rem] pb-[0.15rem] text-wrapper">
		<span class="letters">
			{text}
		</span>
		<span
			class="absolute opacity-0 p-[2px] left-0 height-[2px] w-full bg-white -bottom-2 origin-[100%_100%] line"></span>
	</span>
</svelte:element>
