<script>
	import anime from 'animejs'
	import { onMount } from 'svelte'

	export let animate = 'NONE'
	export let type = 'h1'
	export let text = ''

	export let loop = false
	export let duration = 2000
	export let elasticity = 600
	export let delay = 100

	let element = null
	let letterNodes = null

	onMount(() => {
		let textWrapper = element.querySelector('.letters')
		textWrapper.innerHTML = textWrapper.textContent.replace(
			/\S/g,
			"<span class='origin-[50%_50%] inline-block leading-[1rem] letter'>$&</span>"
		)
		letterNodes = textWrapper.querySelectorAll('.letter')
	})

	$: {
		if (animate == 'ANIMATE') {
			anime.timeline({ loop: loop }).add({
				targets: letterNodes,
				scale: [0, 1],
				duration: duration,
				elasticity: elasticity,
				delay: (el, i) => delay * (i + 1),
			})
		} else if (animate == 'REVERT') {
			anime.timeline({ loop: loop }).add({
				targets: letterNodes,
				scale: 0,
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
	<span class="relative inline-block pt-[0.2rem] pr-[0.05rem] pb-[0.1rem]">
		<span class="letters">
			{text}
		</span>
	</span>
</svelte:element>
