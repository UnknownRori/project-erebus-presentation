<script lang="ts">
	import {Slide, Vertical, Layout, Media} from '@components'
	import TerminalDemo from '../assets/term.mp4'
	import GuiDemo from '../assets/gui.mp4'
</script>

<Vertical>
	<Slide animate animateId="demo">
		<Layout>
			<h1 class="text-6xl">Demo Project</h1>
			<div data-id="border" class="border-2 border-white mt-2 mb-4 w-[50%]"></div>
		</Layout>
	</Slide>

	<Slide>
		<Media class="h-[600px] w-full" src={TerminalDemo} type="video" autoplay />
		<h1 class="text-6xl">Terminal Version</h1>
	</Slide>

	<Slide>
		<Media class="h-[600px] w-full" src={GuiDemo} type="video" autoplay />
		<h1 class="text-6xl">GUI Version</h1>
	</Slide>
</Vertical>
