<script lang="ts">
	import '../app.css';
	import type { PageData } from './$types';
	import Header from '$lib/layout/Header.svelte';
	import Introduction from '$lib/layout/Introduction.svelte';
	import Footer from '$lib/layout/Footer.svelte';
	import Chart from '$lib/charts/layout/Chart.svelte';
	import Card from '$lib/items/Card.svelte';

	import Transactions from '$lib/charts/Transactions.svelte';
	import TransactionVolume from '$lib/charts/TransactionVolume.svelte';
	import TransactionFees from '$lib/charts/TransactionFees.svelte';
	import NewUsers from '$lib/charts/NewUsers.svelte';
	import NewContracts from '$lib/charts/NewContracts.svelte';
	import ContractsbyVol from '$lib/charts/ContractsbyVol.svelte';
	import ContractsbyTransactions from '$lib/charts/ContractsbyTransactions.svelte';
	import ContractsbyUsers from '$lib/charts/ContractsbyUsers.svelte';
	import ChartLanguage from '$lib/charts/language/ChartLanguage.svelte';

	export let data: PageData;
</script>

<body>
	<div class="flex justify-center 2xl:mx-96 3xl:mx-[550px]">
		<div class="grid grid-cols-9 gap-2">
			<div class="col-start-2	col-span-7">
				<Header />
			</div>
			<div class="row-start-2 col-start-2 col-span-7">
				<Introduction />
			</div>
			<div class="row-start-3 col-start-2 col-span-7">
				<Card />
			</div>
			<div class="row-start-4 col-start-1 col-span-9 grid grid-cols-2 gap-2">
				<div class="row-start-1">
					<Chart
						title={'Transactions'}
						query_link={'https://flipsidecrypto.xyz/edit/queries/d2ebbef6-c8fc-432c-a66e-bc869cc7e8fc/visualizations/4bb25d5b-cd07-45d3-8473-0b610f307fd2'}
						description={'Daily and cumulative number of transactions'}
					>
						<div class="h-96" slot="figure">
							<Transactions chart_data={data.DAILY_TRANSACTION_STATS} />
						</div>
					</Chart>
				</div>
				<div class="row-start-1">
					<Chart
						title={'Transaction Fees'}
						query_link={'https://flipsidecrypto.xyz/edit/queries/d2ebbef6-c8fc-432c-a66e-bc869cc7e8fc/visualizations/4bb25d5b-cd07-45d3-8473-0b610f307fd2'}
						description={'Daily and cumulative transaction fees measured in ETH'}
					>
						<div class="h-96" slot="figure">
							<TransactionFees chart_data={data.DAILY_TRANSACTION_STATS} />
						</div>
					</Chart>
				</div>
				<div class="row-start-2 col-span-2 justify-self-center">
					<Chart
						title={'Transaction Volume'}
						query_link={'https://flipsidecrypto.xyz/edit/queries/d2ebbef6-c8fc-432c-a66e-bc869cc7e8fc/visualizations/4bb25d5b-cd07-45d3-8473-0b610f307fd2'}
						description={'Daily and cumulative transaction volume measured in ETH'}
					>
						<div class="h-96" slot="figure">
							<TransactionVolume chart_data={data.DAILY_TRANSACTION_STATS} />
						</div>
					</Chart>
				</div>
				<div class="row-start-3 col-span-2 justify-self-center">
					<ChartLanguage
						><p slot="language">
							The Base testnet has started strongly in terms of users conducting transactions, where
							at time of writing, the testnet has recorded just over 750,000 transactions, with its
							seconds week logging far more transactions than its first.
							<br /> <br />
							What followed this activity is the chain collecting a solid amount of fees measured in
							ETH, totaling at over 180 ETH.
							<br /> <br />
							Although the chain recorded a high amount of transactions in the second week of launch,
							it did not realised into high volume. This suggests that users were conducting a high amount
							of low volume transactions during this period.
						</p></ChartLanguage
					>
				</div>
				<div class="row-start-4 col-span-2 justify-self-center">
					<Chart
						title={'Users'}
						query_link={'https://flipsidecrypto.xyz/edit/queries/ad1f3236-f69a-4d67-a7fe-053aaa880941/visualizations/dac12445-6200-4a2e-b4cd-ed46c928f578'}
						description={'Daily and cumulative new users'}
					>
						<div class="h-96" slot="figure">
							<NewUsers chart_data={data.DAILY_NEW_USERS} />
						</div>
					</Chart>
				</div>
				<div class="row-start-5 col-span-2 justify-self-center">
					<ChartLanguage
						><p slot="language">
							To date, the testnet has amassed just over 160,000 unique users, with significant
							amount of users entering within the past week, probably due to Coinbase's public
							anouncement.
						</p></ChartLanguage
					>
				</div>
				<div class="row-start-6 col-span-2 justify-self-center">
					<Chart
						title={'Contracts'}
						query_link={'https://flipsidecrypto.xyz/edit/queries/6b96b801-d364-40c9-8e8a-9cf24d133d15/visualizations/f252f162-9f07-4a9d-bf86-e0dc5a94564d'}
						description={'Daily and cumulative new contracts'}
					>
						<div class="h-96" slot="figure">
							<NewContracts chart_data={data.DAILY_NEW_CONTRACTS} />
						</div>
					</Chart>
				</div>
				<div class="row-start-7 col-span-2 justify-self-center">
					<ChartLanguage
						><p slot="language">
							The number of contracts being created on the test start strongly but has been
							dwindling ever since. The total number of contracts is over 6000.
						</p></ChartLanguage
					>
				</div>
				<div class="row-start-8">
					<Chart
						title={'Contracts Share by Volume'}
						query_link={'https://flipsidecrypto.xyz/edit/queries/a6e3b8d2-6222-4b4b-a220-f92b2bd5207c/visualizations/eb2e2cee-5705-4cd4-b8b1-d047f7fab19f'}
						description={'Share of volume for each contract'}
					>
						<div class="h-96" slot="figure">
							<ContractsbyVol chart_data={data.CONTRACTS_BY_VOL} />
						</div>
					</Chart>
				</div>
				<div class="row-start-8">
					<Chart
						title={'Contracts Share by Transactions'}
						query_link={'https://flipsidecrypto.xyz/edit/queries/a498782f-0fff-4efd-9594-43d7f68228e8/visualizations/2b85d87e-55d6-4a02-88f1-4adf7c14e765'}
						description={'Share of transactions for each contract'}
					>
						<div class="h-96" slot="figure">
							<ContractsbyTransactions chart_data={data.CONTRACTS_BY_TRANSACTIONS} />
						</div>
					</Chart>
				</div>
				<div class="row-start-9 col-span-2 justify-self-center">
					<Chart
						title={'Contracts Share by Users'}
						query_link={'https://flipsidecrypto.xyz/edit/queries/84956d01-61c3-4917-ad2b-100501a31715/visualizations/bc75dfac-344a-49c5-82c9-426bda05c663'}
						description={'Share of users for each contract'}
					>
						<div class="h-96" slot="figure">
							<ContractsbyUsers chart_data={data.CONTRACTS_BY_USERS} />
						</div>
					</Chart>
				</div>
				<div class="row-start-10 col-span-2 justify-self-center">
					<ChartLanguage
						><p slot="language">
							As contract activity is probably the most important metric on a chain like Base, being
							a layer 2 scaling solution designed to handle higher amounts of activity, we are going
							to examine the share of activity that the top contracts are responsible for.
							<br><br>
							In terms of volume, one contract is responsible for almost all volume transacted thus far.
							<br>
							In terms of number of transactions, it is a little bit more distributed, with one contract being responsible for almost 90% of the total number of transactions conducted.
							<br>
							In terms of number of users, there are two dominant contracts responsible for about 80% of the activity.
						</p></ChartLanguage
					>
				</div>
			</div>
			
		</div>
		
	</div>
	<Footer />
</body>
