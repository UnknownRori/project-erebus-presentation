<script lang="ts">
	import {Slide, Vertical, Layout} from '@components'
	import TextLineSpawnEffect from '../components/TextLineSpawnEffect.svelte'
	import ShuntingYard from '../assets/shunting-yard.svelte'

	let animateTitle = 'NONE'
	let animateContent = 'NONE'
</script>

<Vertical>
	<Slide on:in={()=> (animateTitle = 'ANIMATE')} animate animateId="algorithm">
		<Layout>
			<TextLineSpawnEffect animate={animateTitle} class="text-6xl" text="Shunting Yard Algorithm" />
		</Layout>
	</Slide>

	<Slide on:in={()=> {
		animateContent = 'ANIMATE'
		animateTitle = 'ANIMATE'
		}}
		on:out={() => {
		animateTitle = 'REVERT'
		animateContent = 'REVERT'
		}}
		animate
		animateId="algorithm"
		>
		<Layout>
			<TextLineSpawnEffect animate={animateTitle} class="text-6xl" text="Shunting Yard Algorithm" />
			<TextLineSpawnEffect animate={animateContent} type="p" durationLine={2000} durationLetters={100}
				class="text-5xl text-left mt-2" text="
				Merupakan algoritma ber-datastructure Stack yang diciptakan oleh Edsger
				Dijkstra, algoritma ini digunakan untuk melakukan parsing terhadap
				expresi matematika dan logika dengan notasi Infix Notation, dan
				algoritma ini menghasilkan Postfix Notation (Reverse Polish Notation)
				atau Abstract Syntax Tree (AST).
			" />
		</Layout>
	</Slide>

	<Slide animate animateId="algorithm">
		<Layout>
			<ShuntingYard></ShuntingYard>
		</Layout>
	</Slide>
</Vertical>
