<script lang="ts">
	import anime from 'animejs'

	import {Slide, Vertical, Layout} from '@components'
	import TextEffectSlow from '../components/TextEffectSlow.svelte'

	let animateTitle = 'NONE'
	let animateLine = 'NONE'
	let element = null
	$: {
		if (animateLine == 'ANIMATE') {
			anime({
				targets: element,
				scaleX: 80,
				duration: 500,
				elasticity: 800,
				delay: 1500,
			})
		}
	}
</script>

<Vertical>
	<Slide on:in={()=> {
		animateTitle = 'ANIMATE'
		animateLine = 'ANIMATE'
		}}
		on:out={() => {
		animateTitle = 'REVERT'
		animateLine = 'REVERT'
		}}
		animate
		animateId="end"
		>
		<Layout>
			<TextEffectSlow animate={animateTitle} duration={1000} class="text-[6rem] font-bold tracking-wide"
				text="Fin" />
			<div bind:this={element} data-id="line" class="h-[0.25rem] w-[0.25rem] bg-white test"></div>
		</Layout>
	</Slide>
</Vertical>
