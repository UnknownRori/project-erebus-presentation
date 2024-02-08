<script lang="ts">
	import {Slide, Vertical, Layout} from '@components'

	import TextDropEffect from '../components/TextDropEffect.svelte'
	import TextSlowAppearEffect from '../components/TextSlowAppearEffect.svelte'

	let animateMainTitle = 'NONE'
	let animateSubtitle = 'NONE'
</script>

<Vertical>
	<Slide animate animateId="intro">
		<Layout>
			<div data-id="border" class="border-4 border-white w-[80%]"></div>
		</Layout>
	</Slide>

	<Slide on:in={()=> {
		animateMainTitle = 'ANIMATE'
		animateSubtitle = 'ANIMATE'
		}}
		on:out={() => {
		animateSubtitle = 'REVERT'
		animateMainTitle = 'REVERT'
		}}
		animate
		animateId="intro"
		>
		<Layout>
			<TextDropEffect animate={animateMainTitle} duration={100} text="Project - Ἔρεβος"
				customClass="text-8xl font-bold tracking-wider" />
			<TextSlowAppearEffect animate={animateSubtitle} duration={1800}
				class="tracking-widest leading-loose text-6xl text-left" text="Project - Erebus" />
			<div data-id="border" class="border-2 border-white w-[50%]"></div>
		</Layout>
	</Slide>

	<Slide animate animateId="intro">
		<Layout>
			<div data-id="border" class="border-2 border-white w-[50%]"></div>
			<h1 class="text-8xl">Kelompok 4</h1>
		</Layout>
	</Slide>

	<Slide animate animateId="intro">
		<Layout>
			<h1 class="text-8xl">Kelompok 4</h1>
			<table>
				<tr>
					<td>Akbar Hendra Jaya</td>
					<td>2212030549</td>
				</tr>
				<tr>
					<td>Ali Akbar Poetra R</td>
					<td>2212030569</td>
				</tr>
				<tr>
					<td>Pradipta Arya Pratama</td>
					<td>2212030540</td>
				</tr>
				<tr>
					<td>Yuha Bani Abid</td>
					<td>2212030552</td>
				</tr>
			</table>
			<div data-id="border" class="border-2 border-white w-[80%]"></div>
		</Layout>
	</Slide>
</Vertical>
