<script lang="ts">
	import { Slide, Vertical, Layout, Media } from '@components'
	import Poster from '../assets/poster.jpeg'
	import TouhouDemo from '../assets/touhou.mp4'
</script>

<!-- Promosi -->
<!-- Poster -->
<!-- Game -->
<!-- License -->
<!-- Demo -->

<Vertical>
	<Slide animate animateId="promotion">
		<Layout>
			<h1 class="text-6xl">Promosi</h1>
			<div
				data-id="border"
				class="border-2 border-white mt-2 mb-4 w-[50%]"
			></div>
		</Layout>
	</Slide>

	<Slide animate animateId="promotion">
		<Layout>
			<h1 class="text-6xl">暗い Project</h1>
			<img src={Poster} alt="Poster" class="w-[45%] object-cover" />
		</Layout>
	</Slide>

	<Slide animate animateId="promotion">
		<Layout>
			<h1 class="text-6xl my-2">暗い Project</h1>
			<div class="h-screen flex items-center justify-center gap-8">
				<Media class="w-[25vw]" src={TouhouDemo} type="video" autoplay />
				<p class="text-left my-2">
					暗い (Kurai) Project merupakan fan game open source bertema Touhou
					Project, Game ini bergenre Shoot ‘em up game (STG) atau sering disebut
					Danmaku atau Bullet Hell, Game ini berfokus dalam pengenalan pola dan
					penguasaan melalui latihan.
				</p>
			</div>
		</Layout>
	</Slide>

	<!-- <Slide animate animateId="promotion"> -->
	<!-- 	<Layout> -->
	<!-- 		<h1 class="text-6xl my-2">暗い Project</h1> -->
	<!-- 		<p class="text-left my-2"> -->
	<!-- 			Kurai Project ini ditulis menggunakan bahasa pemrograman Rust tanpa -->
	<!-- 			menggunakan Game Engine. Game ini cross platform Linux, Mac, Windows, -->
	<!-- 			dan juga di Web -->
	<!-- 		</p> -->
	<!-- 	</Layout> -->
	<!-- </Slide> -->

	<Slide animate animateId="promotion">
		<Layout>
			<Media
				class="h-[600px] w-full"
				src="https://unknownrori.github.io/kurai-project/"
				type="iframe"
			/>
		</Layout>
	</Slide>
</Vertical>
