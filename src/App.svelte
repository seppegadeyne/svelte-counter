<script>
	export let name;

	import { onMount } from 'svelte';

	function count(node) {
		node.innerText = parseInt(node.innerText) + parseInt(node.dataset.steps);
	}

	onMount(() => {
		document.querySelectorAll('div[data-count]').forEach(node => {
			const interval = setInterval(() => {
				if (parseInt(node.innerText) < node.dataset.count) {
					count(node);
				} else {
					clearInterval(interval);
				}
			}, node.dataset.delay);

		})
	});
</script>

<main>
	<h2>Enkele cijfers...</h2>
	<section>
		<div>
			<div>
				<div data-count="11" data-delay="75" data-steps="1">0</div>
				<div>mio</div>
			</div>
			<p>datapunten per maand geanalyseerd</p>
		</div>
		<div>
			<div>
				<div data-count="300000" data-delay="1" data-steps="500">0</div>
			</div>
			<p>views per vacature campagne</p>
		</div>
		<div>
			<div>
				<div data-count="80" data-delay="15" data-steps="1">0</div>
				<div>%</div>
			</div>
			<p>van vacatures ingevuld in 2019</p>
		</div>
		<div>
			<div>
				<div data-count="45" data-delay="15" data-steps="1">0</div>
			</div>
			<p>sollicitanten per vacature binnen 30 dagen (gemiddeld)</p>
		</div>
		<div>
			<div>
				<div data-count="7" data-delay="75" data-steps="1">0</div>
			</div>
			<p>7 landen (and counting)</p>
		</div>
		<div>
			<div>
				<div data-count="75" data-delay="15" data-steps="1">0</div>
				<div>%</div>
			</div>
			<p>75% terugkerende klanten</p>
		</div>
	</section>
</main>

<style>
	main {
		text-align: center;
	}
	main h2 {
		font-size: 32px;
		font-weight: 700;
		margin-bottom: 4rem;
	}
	section {
		display: grid;
		gap: 2rem;
		grid-template-columns: 1fr 1fr 1fr;
		grid-auto-rows: 1fr;
	}
	section > div > div {
		display: flex;
		justify-content: center;
		color: #FB4C5A;
		font-weight: 600;
		font-size: 60px;
	}
	p {
		text-align: center;
		color: #666666;
	}
</style>