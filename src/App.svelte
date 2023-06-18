<script lang="ts">
	import Tabs from './lib/Tabs.svelte';

	const tabs = [
		{
			title: 'JStillery',
			url: 'https://mindedsecurity.github.io/jstillery/',
		},
		{
			title: 'de4js',
			url: 'https://lelinhtinh.github.io/de4js',
		},
		{
			title: 'JavaScript Deobfuscator',
			url: 'https://deobfuscate.io/',
		},
		{
			title: 'Closure Compiler',
			url: 'https://closure-compiler.appspot.com/home',
		},
	];
</script>

<main>
	<Tabs tabs="{tabs}" />
</main>

<style>
	main {
		height: 100vh;
		display: grid;
		grid-template-rows: 46px 1fr;
	}
</style>
