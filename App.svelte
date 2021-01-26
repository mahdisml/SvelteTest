<script>
	import Timer from "./Timer.svelte";
	import {Core} from "./Core";
	import {getContext, setContext} from "svelte";

	setContext('core',new Core())
	let core = getContext('core')
	let time = core.time

	setInterval(function () {
		$time++
	}, 1000);
</script>

<main>
	<h1>Timer = {$time}</h1>
	<Timer/>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>