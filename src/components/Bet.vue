<template>
	<div>
		<div class="container mx-auto max-w-7xl px-5 py-20">
				<div class="mb-8 2xl:mb-20 text-center py-10">
					<h2 class="nl-title mb-12 font-heading font-bold text-3xl md:text-5xl leading-none">Recent Winners</h2>
				</div>

			<div class="overflow-x-auto">
				<table class="table table-zebra w-full">
					<thead>
						<tr>
							<th>COIN</th>
							<th>Address</th>
							<th>Amount</th>
							<th>TXN</th>
						</tr>
					</thead>
					<tbody>
						<tr v-for="item in busd" :key="item.txn">
							<td><div class="badge badge-secondary  badge-outline">BUSD</div></td>
							<td>{{ item.address }}</td>
							<td>{{ item.amount / 1000000000000000000 }}</td>
							<td><a target="_blank" :href="'https://bscscan.com/tx/' + item.txn">VIEW</a></td>
						</tr>

						<tr v-for="item in usdt" :key="item.txn">
							<td><div class="badge badge-primary badge-outline">USDT</div></td>
							<td>{{ item.address }}</td>
							<td>{{ item.amount / 1000000000000000000 }}</td>
							<td><a target="_blank" :href="'https://bscscan.com/tx/' + item.txn">VIEW</a></td>
						</tr>
					</tbody>
				</table>
			</div>
		</div>
	</div>
</template>

<script>
	import axios from 'axios';

	async function fetch(var1) {
		const rr = await axios({
			url: 'https://api.thegraph.com/subgraphs/name/nolossclub/' + var1,
			method: 'post',
			data: {
				query: `
	           {
	             winners(first: 10) {
	               id
	               txn
	               address
	               amount
	             }
	           }
	           `,
			},
		}).then((res) => res.data.data.winners);

		console.log(rr[0]);
		return rr;
	}

	export default {
		data() {
			return {
				busd: [],
				usdc: [],
				usdt: [],
			};
		},
		methods: {},
		async mounted() {
			const data_busd = await fetch('busd');
			const data_usdt = await fetch('usdt');

			this.busd = data_busd;
			this.usdt = data_usdt;
		},
	};
</script>
