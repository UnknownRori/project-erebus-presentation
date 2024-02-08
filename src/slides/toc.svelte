<script lang="ts">
	import {Slide, Vertical, Step, Layout} from '@components'
</script>

<Vertical>
	<Slide animate animateId="toc">
		<Layout>
			<h1 class="text-6xl">TOC</h1>
			<h2 class="text-5xl">Table of Contents</h2>
			<div data-id="border" class="border-2 border-white w-[30%]"></div>
		</Layout>
	</Slide>

	<Slide animate animateId="toc">
		<Layout>
			<h1 class="text-6xl">TOC</h1>
			<h2 class="text-5xl">Table of Contents</h2>
			<div data-id="border" class="border-2 border-white w-[50%]"></div>
			<ul class="list-decimal text-left flex flex-col gap-2">
				<Step>
					<li>Permasalahan</li>
				</Step>
				<Step>
					<li>Tujuan Project</li>
				</Step>
				<Step>
					<li>Demo Project</li>
				</Step>
				<Step>
					<li>Shunting Yard Algoritma</li>
				</Step>
				<Step>
					<li>Flowchart</li>
				</Step>
			</ul>
		</Layout>
	</Slide>
</Vertical>
