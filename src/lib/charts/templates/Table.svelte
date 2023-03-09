<script lang="ts">
	import Grid from 'gridjs-svelte';
	import { css } from '@emotion/css';
	import { onMount } from 'svelte';
	import ChartHeader from '$lib/charts/layout/ChartHeader.svelte';

	export let title: any;
	export let query_link: any;

	//export let table_data: any;

	const columns = ['Rank', 'Pool', 'Total Value Locked'];
	const data = [
		[1, 'ILV / WETH', '$64.85m'],
		[2, 'USDC / WETH', '$49.57m'],
		[3, 'MAGIC / WETH', '$26.86m'],
		[4, 'WETH / USDC', '$24.98m'],
		[5, 'WETH / USDT', '$19.48m'],
	];
	const className = {
		container: css`
			* {
				font-family: 'Quicksand';
			}
		`,
		table: css`
			width: 100%;
			margin-top: 2px;
			tr:nth-child(even) {
				background-color: rgba(0, 0, 0, 0.1);
			};
            tr:nth-child(1) {
                width: 10px
            }
			outline: 2px solid;
			border-top-left-radius: 10px;
			border-top-right-radius: 10px;
			border-bottom-right-radius: 10px;
			border-bottom-left-radius: 10px;
		`,
		th: css`
			background-color: #a8a29e;
			text-align: center;
			padding: 15px;
			&:nth-child(1) {
				border-top-left-radius: 10px;
			}
			&:nth-child(3) {
				border-top-right-radius: 10px;
			}
		`,
		td: css`
			text-align: center;
			padding: 7px;
            &:nth-child(1) {
                width: 1px;
            }
		`,
		header: css``
	};
    const sort = true;
    //const pagination = {limit: 10};
    const fixedHeader = true;
</script>

<div class="border-2 border-stone-500 px-6 rounded-lg bg-white pb-4">
	<div class="p-2">
		<ChartHeader {title} {query_link} />
	</div>

	<div class="relative flex-auto">
		<Grid {columns} {data} {className} {fixedHeader}/>
	</div>
</div>
