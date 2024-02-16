<script lang="ts">
	import anime from 'animejs'

	import {Slide, Vertical, Step, Layout} from '@components'
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
		animate
		animateId="requirement"
		>
		<Layout>
			<TextEffectSlow data-id="tooling" animate={animateTitle} duration={1000}
				class="text-[6rem] font-bold tracking-wide" text="Tooling" />
			<div bind:this={element} data-id="tooling-line" class="h-[0.25rem] w-[0.25rem] bg-white test"></div>
		</Layout>
	</Slide>

	<Slide on:in={()=> {
		animateTitle = 'ANIMATE'
		animateLine = 'ANIMATE'
		}}
		animate
		animateId="requirement"
		>
		<Layout>
			<TextEffectSlow data-id="tooling" animate={animateTitle} duration={1000}
				class="text-[6rem] font-bold tracking-wide" text="Tooling" />
			<div data-id="tooling-line" class="h-[0.25rem] w-[50%] bg-white"></div>
			<ul class="flex flex-col gap-4 list-decimal text-left">
				<Step>
					<li>C++ 2020</li>
				</Step>
				<Step>
					<li>g++ 17</li>
				</Step>
				<Step>
					<li>Neovim + Rori.nvim</li>
				</Step>
				<Step>
					<li>Raylib</li>
				</Step>
				<Step>
					<li>Emscripten</li>
				</Step>
			</ul>
		</Layout>
	</Slide>
</Vertical>
