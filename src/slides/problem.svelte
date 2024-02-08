<script lang="ts">
	import {Slide, Vertical, Step, Layout} from '@components'
	import TextLineSpawnEffect from '../components/TextLineSpawnEffect.svelte'
	let animateTitle = 'NONE'
</script>

<Vertical>
	<Slide on:in={()=> (animateTitle = 'ANIMATE')} animate animateId="problem">
		<Layout>
			<TextLineSpawnEffect animate={animateTitle} class="text-6xl" text="Permasalahan" />
		</Layout>
	</Slide>

	<Slide on:in={()=> (animateTitle = 'ANIMATE')}
		on:out={() => {
		animateTitle = 'REVERT'
		}}
		animate
		animateId="problem"
		>
		<Layout>
			<TextLineSpawnEffect animate={animateTitle} class="text-6xl" text="Permasalahan" />
			<ul class="list-decimal text-left flex flex-col gap-4">
				<Step>
					<li>Susahnya menghitung expresi/rumus matematika yang panjang.</li>
				</Step>
				<Step>
					<li>
						Susahnya ketika tidak ada akses internet untuk mengakses wolfram
						atau kalkulator tidak mensupport logika matematika yang kompleks
					</li>
				</Step>
				<Step>
					<li>
						Mungkin saja lelah mengoperasikan operasi matematika satu persatu di
						kalkulator.
					</li>
				</Step>
			</ul>
		</Layout>
	</Slide>
</Vertical>
