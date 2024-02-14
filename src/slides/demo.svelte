<script lang="ts">
	import { Slide, Vertical, Layout, Media } from '@components'
	import TerminalDemo from '../assets/term.mp4'
	import GuiDemo from '../assets/gui.mp4'
</script>

<Vertical>
	<Slide animate animateId="demo">
		<Layout>
			<h1 class="text-6xl">Demo Project</h1>
			<div
				data-id="border"
				class="border-2 border-white mt-2 mb-4 w-[50%]"
			></div>
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

	<Slide>
		<Media
			class="h-[600px] w-full"
			src="https://unknownrori.github.io/project-erebus/"
			type="iframe"
		/>
		<h1 class="text-6xl">Web Version</h1>
	</Slide>

	<Slide>
		<Layout>
			<h1 class="text-6xl">Download & Source Code</h1>
			<a
				class="text-blue-300"
				href="https://github.com/UnknownRori/project-erebus"
				>https://github.com/UnknownRori/project-erebus</a
			>

			<h1 class="text-6xl mt-20">Web Version (Experimental)</h1>
			<a
				class="text-blue-300"
				href="https://unknownrori.github.io/project-erebus/"
				>https://unknownrori.github.io/project-erebus/</a
			>
		</Layout>
	</Slide>
</Vertical>
