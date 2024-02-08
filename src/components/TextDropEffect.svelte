<script>
	import anime from 'animejs'
	import { onMount } from 'svelte'

	export let animate = 'NONE'
	export let type = 'h1'
	export let text = ''
	export let customClass = ''

	export let loop = false
	export let duration = 2000
	export let delay = 200

	let element = null
	let letterNodes = null

	onMount(() => {
		element.innerHTML = element.textContent.replace(
			/\S/g,
			"<span class='inline-block leading-[1rem] letter'>$&</span>"
		)
		letterNodes = element.querySelectorAll('.letter')
	})

	$: {
		if (animate == 'ANIMATE') {
			anime.timeline({ loop: loop }).add({
				targets: letterNodes,
				translateY: [-200, 0],
				easing: 'easeOutExpo',
				duration: duration,
				delay: (el, i) => delay * i,
			})
		} else if (animate == 'REVERT') {
			anime.timeline().add({
				targets: letterNodes,
				translateY: -100,
			})
		}
	}
</script>

<svelte:element
	this={type}
	bind:this={element}
	class={customClass + ' overflow-hidden p-2'}
	{...$$restProps}
>
	{text}
</svelte:element>
