<script>
	import anime from 'animejs'
	import { onMount } from 'svelte'

	export let animate = 'NONE'
	export let type = 'h1'
	export let text = ''

	export let loop = false
	export let duration = 500
	export let delay = 50

	let element = null

	onMount(() => {
		element.innerHTML = element.textContent.replace(
			/\S/g,
			"<span class='letter'>$&</span>"
		)
	})

	$: {
		if (animate == 'ANIMATE') {
			anime.timeline({ loop: loop }).add({
				targets: element.querySelectorAll('.letter'),
				opacity: [0, 1],
				easing: 'easeInOutQuad',
				duration: duration,
				delay: (el, i) => delay * (i + 1),
			})
		} else if (animate == 'REVERT') {
			anime.timeline().add({
				targets: element.querySelectorAll('.letter'),
				opacity: 0,
				easing: 'easeOutExpo',
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
	{text}
</svelte:element>
