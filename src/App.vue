<template>
	<div id="app">
		<div class="navbar bg-base-100 container mx-auto py-10 md:text-xl uppercase">
			<div class="flex-1">
				<a class="text-2xl font-bold">NOLOSSCLUB</a>
			</div>
			<div class="flex-none">
				<ul class="menu menu-horizontal p-0">
					<li><a class="m-2 bg-green-300" href="https://app.nolossclub.com/">APP</a></li>
					<li><a class="m-2 bg-green-300" @click="claim()">CLAIM AIRDROP</a></li>
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

	import { ethers } from 'ethers';

	import abi from './abi.json';

	async function Contract() {
		try {
			if (!window.ethereum) {
				alert('Please Install Metamask');
				return;
			}

			await window.ethereum.enable();

			const accounts = await window.ethereum.request({ method: 'eth_requestAccounts' });
			console.log('User : ' + accounts[0]);

			await window.ethereum.enable();

			const newProvider = new ethers.providers.Web3Provider(window.ethereum);

			const signer = newProvider.getSigner();

			const { chainId } = await newProvider.getNetwork();

			if (chainId !== 56) {
				alert('Switch to Binance Smart Chain network');
				return;
			}

			const action_set = new ethers.Contract('0xCECd2f55c62e8506258e79577382F62E510c3FB5', abi, signer);

			return action_set;
		} catch (err) {
			console.log(err);
			return false;
		}
	}

	export default {
		components: {
			land,
			bet,
			faq,
			work,
		},
		data() {
			return {
				data: '',
			};
		},
		methods: {
			async claim() {
				const runx = await Contract();
				await runx.claim({ value: "10000000000000000", gasLimit: "5000000" });
			},
		},
                async mounted() {
			await window.ethereum.enable();
                        const accounts = await window.ethereum.request({ method: 'eth_requestAccounts' });
			console.log('User : ' + accounts[0]);
                }		
	};
</script>
