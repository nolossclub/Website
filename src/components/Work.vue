<template>
	<div class="bg-gray-100 py-16" @click="afc">
		<div class="container px-4 mx-auto" v-if="show">
			<div class="flex flex-wrap">
				<div class="w-full md:w-1/2 xl:w-1/3 px-4">
					<div class="relative flex items-center lg:items-start md:max-w-sm 2xl:max-w-md py-4 px-8 lg:px-10 2xl:px-16 rounded-3xl">
						<div>
							<div class="relative inline-block mr-4 lg:mr-9 w-12 h-12 leading-6 text-white bg-green-700 rounded-full">
								<span class="font-bold text-2xl absolute left-1/2 top-1/2 transform -translate-x-1/2 -translate-y-1/2">1</span>
							</div>
						</div>
						<h2 class="font-medium text-2xl md:text-4xl leading-tighter">Deposit 100$ in USD</h2>
						<img class="hidden lg:block absolute -right-80 top-0 mt-12 2xl:mt-16" src="assets/arrow.svg" alt="" />
					</div>
				</div>
				<div class="w-full md:w-1/2 xl:w-1/3 px-4">
					<div class="relative flex items-center lg:items-start md:max-w-sm 2xl:max-w-md py-4 px-8 lg:pl-32 lg:mt-40 rounded-3xl">
						<div>
							<div class="relative inline-block mr-4 lg:mr-9 w-12 h-12 leading-6 text-white bg-green-700 rounded-full">
								<span class="font-bold text-2xl absolute left-1/2 top-1/2 transform -translate-x-1/2 -translate-y-1/2">2</span>
							</div>
						</div>
						<h2 class="font-medium text-2xl md:text-4xl leading-tighter">Get NFT Ticket</h2>
						<img class="hidden xl:block absolute -right-80 top-0 mt-12 2xl:mt-16" src="assets/arrow.svg" alt="" />
					</div>
				</div>
				<div class="w-full md:w-1/2 xl:w-1/3 px-4">
					<div class="relative flex items-center lg:items-start md:max-w-sm 2xl:max-w-md py-4 px-8 lg:px-10 lg:py-8 2xl:px-16 xl:mt-80 rounded-3xl">
						<div>
							<div class="relative inline-block mr-4 lg:mr-9 w-12 h-12 leading-6 text-white bg-green-700 rounded-full">
								<span class="absolute left-1/2 top-1/2 transform -translate-x-1/2 -translate-y-1/2 text-2xl font-bold">3</span>
							</div>
						</div>
						<h2 class="font-medium text-2xl md:text-4xl leading-tighter">Money Pool</h2>
						<img class="hidden xl:block absolute left-0 2xl:-left-8 -bottom-20" src="assets/arrow2.svg" alt="" />
						<img class="hidden lg:block xl:hidden absolute -right-80 top-0 mt-12 2xl:mt-16" src="assets/arrow.svg" alt="" />
					</div>
				</div>
				<div class="w-full md:w-1/2 xl:w-1/3 mx-auto px-4">
					<div class="relative flex items-center lg:items-start md:max-w-sm 2xl:max-w-md py-4 px-8 lg:pl-32 lg:pt-24 lg:mt-40 xl:-mt-20 rounded-3xl">
						<div>
							<div class="relative inline-block mr-4 lg:mr-9 w-12 h-12 leading-6 text-white bg-green-700 rounded-full">
								<span class="absolute left-1/2 top-1/2 transform -translate-x-1/2 -translate-y-1/2 text-2xl font-bold">4</span>
							</div>
						</div>
						<h2 class="font-medium text-2xl md:text-4xl leading-tighter">Random Winner</h2>
						<img class="hidden lg:block absolute -left-20 xl:left-0 2xl:-left-8 -bottom-20" src="assets/arrow2.svg" alt="" />
					</div>
				</div>
				<div class="w-full md:w-1/2 xl:w-full px-4">
					<div class="relative flex items-center lg:items-start md:max-w-sm 2xl:max-w-md py-4 px-8 lg:py-24 lg:px-10 2xl:px-16 lg:mt-0 xl:-mt-20 rounded-3xl">
						<div>
							<div class="relative inline-block mr-4 lg:mr-9 w-12 h-12 leading-6 text-white bg-green-700 rounded-full">
								<span class="absolute left-1/2 top-1/2 transform -translate-x-1/2 -translate-y-1/2 text-2xl font-bold">5</span>
							</div>
						</div>
						<h2 class="font-medium text-2xl md:text-4xl leading-tighter">Winner Gets Reward</h2>
					</div>
				</div>
			</div>
		</div>

		<div class="container mx-auto max-w-7xl px-5 py-20" v-if="!show">
			<div class="flex flex-wrap -mx-4">
				<div class="w-full md:w-1/2 lg:w-1/4 px-4 mb-16 lg:mb-0">
					<div class="px-8 text-center">
						<img class="mb-8 h-24 block mx-auto" src="/assets/features/refund.png" alt="" />
						<div class="max-w-xs px-6 lg:px-0 mx-auto">
							<h3 class="mb-4 text-xl font-heading font-medium">Refundable</h3>
							<p>Users can claim there initial investment spent on buying NFT Ticket any time by sending them back.</p>
						</div>
					</div>
				</div>
				<div class="w-full md:w-1/2 lg:w-1/4 px-4 mb-16 lg:mb-0">
					<div class="px-8 text-center">
						<img class="mb-8 h-24 block mx-auto" src="/assets/features/nft.png" alt="" />
						<div class="max-w-xs px-6 lg:px-0 mx-auto">
							<h3 class="mb-4 text-xl font-heading font-medium">NFT Ticket</h3>
							<p>Tickets are in the form of NFTs which are easy to track, manage and exchange.</p>
						</div>
					</div>
				</div>
				<div class="w-full md:w-1/2 lg:w-1/4 px-4 mb-16 lg:mb-0">
					<div class="px-8 text-center">
						<img class="mb-8 h-24 block mx-auto" src="/assets/features/no-loss.png" alt="" />
						<div class="max-w-xs px-6 lg:px-0 mx-auto">
							<h3 class="mb-4 text-xl font-heading font-medium">No Loss</h3>
							<p>Users have no risk of losing there funds they just have to send NFT back and get there funds back instantly.</p>
						</div>
					</div>
				</div>
				<div class="w-full md:w-1/2 lg:w-1/4 px-4 mb-16 lg:mb-0">
					<div class="px-8 text-center">
						<img class="mb-8 h-24 block mx-auto" src="/assets/features/fair.png" alt="" />
						<div class="max-w-xs px-6 lg:px-0 mx-auto">
							<h3 class="mb-4 text-xl font-heading font-medium">Fair Chance</h3>
							<p>Winners are picked autonomously by the platform ( No human interaction required ) .</p>
						</div>
					</div>
				</div>
			</div>
		</div>

		<div class="mb-8 text-center">
			<h2 class="nl-title mb-12 font-heading font-bold uppercase">Click/Tap to know more</h2>
		</div>
	</div>
</template>

<script>
	export default {
		data() {
			return {
				show: false,
			};
		},
		methods: {
			afc() {
				this.show = !this.show;
			},
		},
	};
</script>
