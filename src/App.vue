<template>
	<div id="app">
		<div class="navbar bg-base-100 container mx-auto py-10 md:text-xl uppercase">
			<div class="flex-1">
				<a class="text-2xl font-bold">NOLOSSCLUB</a>
			</div>
			<div class="flex-none">
				<ul class="menu menu-horizontal p-0">
					<li><a class="m-2 bg-green-300" href="https://app.nolossclub.com/">APP</a></li>
					<li><a class="m-2 bg-green-300" href="https://discord.gg/rs862d6wsA">Discord</a></li>
				</ul>
			</div>
		</div>

		<land />
		<work />
		<bet />
		<faq />

		<section id="contact" class="py-8">
			<div class="container mx-auto px-6 pt-6 pb-6">
				<div class="flex flex-wrap items-center justify-center">
					<a class="m-5 inline-flex items-center pb-2 font-bold tracking-tight text-xl leading-6 text-green-600 hover:text-green-700 border-b border-green-600 hover:border-green-700" href="https://twitter.com/nolossclub">
						<span class="mr-3">Twitter</span>
						<svg width="16" height="13" viewBox="0 0 16 13" fill="none" xmlns="http://www.w3.org/2000/svg">
							<path d="M10.8 1L15 7H1" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"></path>
							<path d="M11 12L15 7" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"></path>
						</svg>
					</a>
					<a class="m-5 inline-flex items-center pb-2 font-bold tracking-tight text-xl leading-6 text-green-600 hover:text-green-700 border-b border-green-600 hover:border-green-700" href="https://github.com/nolossclub">
						<span class="mr-3">Github</span>
						<svg width="16" height="13" viewBox="0 0 16 13" fill="none" xmlns="http://www.w3.org/2000/svg">
							<path d="M10.8 1L15 7H1" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"></path>
							<path d="M11 12L15 7" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"></path>
						</svg>
					</a>
					<a class="m-5 inline-flex items-center pb-2 font-bold tracking-tight text-xl leading-6 text-green-600 hover:text-green-700 border-b border-green-600 hover:border-green-700" href="https://discord.gg/rs862d6wsA">
						<span class="mr-3">Discord</span>
						<svg width="16" height="13" viewBox="0 0 16 13" fill="none" xmlns="http://www.w3.org/2000/svg">
							<path d="M10.8 1L15 7H1" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"></path>
							<path d="M11 12L15 7" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"></path>
						</svg>
					</a>
				</div>
			</div>
		</section>
	</div>
</template>

<script>
	import land from './components/Land.vue';
	import bet from './components/Bet.vue';
	import faq from './components/Faq.vue';
	import work from './components/Work.vue';

	export default {
		name: 'App',
		components: {
			land,
			bet,
			faq,
			work,
		},
	};
</script>
