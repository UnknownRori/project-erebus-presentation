<script>
	import anime from 'animejs'
	import { onMount } from 'svelte'

	export let animate = 'NONE'
	export let type = 'h1'
	export let text = ''

	export let loop = false
	export let duration = 300

	let element = null

	onMount(() => {
		let textWrapper = element.querySelector('.letters')
		textWrapper.innerHTML = textWrapper.textContent.replace(
			/([^a-zA-Z]|\w)/g,
			"<span class='letter'>$&</span>"
		)
	})

	$: {
		if (animate == 'ANIMATE') {
			anime.timeline({ loop: loop }).add({
				targets: element.querySelectorAll('.letter'),
				opacity: [0, 1],
				easing: 'easeOutExpo',
				duration: duration,
				offset: '-=775',
				delay: (el, i) => 34 * (i + 1),
			})
		} else if (animate == 'REVERT') {
			anime.timeline({ loop: loop }).add({
				targets: element.querySelectorAll('.letter'),
				opacity: 0,
				easing: 'easeOutExpo',
				duration: 1,
				offset: '-=775',
				delay: 0,
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
	<span class="relative inline-block pt-[0.1rem] pr-[0.05rem] pb-[0.15rem]">
		<span class="letters">
			{text}
		</span>
	</span>
</svelte:element>
