<script lang="ts">
	import Blobity from 'blobity'
	import {Presentation} from '@components'
	import {
		Intro,
		Toc,
		Problem,
		Target,
		Tooling,
		Demo,
		Algorithm,
		Flowchart,
		End,
	} from './slides/index'

	new Blobity({
		invert: true,
		dotColor: '#3CCF91',
		font: 'Fira Code',
		fontSize: 13,
	})
</script>

<Presentation>
	<Intro />
	<Toc />
	<Problem />
	<Target />
	<Tooling />
	<Demo />
	<Algorithm />
	<Flowchart />
	<End />
</Presentation>
