<template>
	<div class="container mx-auto max-w-7xl px-5">
		<div class="py-10">
			<div class="flex md:flex-row flex-col items-center">
				<div class="md:w-1/2 p-5">
					<p class="text-3xl font-bold uppercase text-gray-600">NOLOSSCLUB is a crypto-powered savings protocol based on Defi lending. Save money and have a chance to win every week.</p>
					<div class="py-5">
						<div class="stats shadow">
							<div class="stat place-items-center">
								<div class="stat-value">TVL</div>
							</div>

							<div class="stat place-items-center">
								<div class="stat-title">BUSD</div>
								<div class="stat-value">{{ busd }} $</div>
							</div>

							<div class="stat place-items-center">
								<div class="stat-title">USDT</div>
								<div class="stat-value">{{ usdt }} $</div>
							</div>

							<div class="stat place-items-center">
								<div class="stat-title">USDC</div>
								<div class="stat-value">{{ usdc }} $</div>
							</div>
						</div>
					</div>
				</div>

				<div class="md:w-1/2 p-5">
					<lottie-player class="object-cover object-center" autoplay="" loop="" mode="normal" src="/assets/1.json" background="transparent"></lottie-player>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
	import { ethers } from 'ethers';
	import abi from '../assets/nft.json';

	export default {
		data() {
			return {
				busd: 0,
				usdc: 0,
				usdt: 0,
			};
		},
		async mounted() {
			const provider = new ethers.providers.JsonRpcProvider('https://bsc-dataseed1.ninicoin.io');

			const Contract_BUSD = await new ethers.Contract('0x165a3cda295784c195746e3b267602eede1fc901', abi, provider);
			const Contract_USDT = await new ethers.Contract('0xE91DB8abe66613571c05471bfc358f15DAFBc4dB', abi, provider);
			const Contract_USDC = await new ethers.Contract('0xbD310c711602A605b8cd888240398478dA28b387', abi, provider);

			var busd = await Contract_BUSD.totalSupply();
			this.busd = (busd.toString() * 100).toFixed(0);

			var usdt = await Contract_USDT.totalSupply();
			this.usdt = (usdt.toString() * 100).toFixed(0);

			var usdc = await Contract_USDC.totalSupply();
			this.usdc = (usdc.toString() * 100).toFixed(0);
		},
	};
</script>
