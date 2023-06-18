<script lang="ts">
	type Tab = {
		title: string;
		url: string;
	};
	export let tabs: Tab[];
	export let activeTabValue: number = 0;
	const handleClick = (tabValue: number) => () => (activeTabValue = tabValue);
</script>

<ul>
	<h2>Deobfuscation Tools</h2>
	{#each tabs as tab, i}
		<li class="{activeTabValue === i ? 'active' : ''}">
			<!-- svelte-ignore a11y-click-events-have-key-events -->
			<span on:click="{handleClick(i)}">{tab.title}</span>
		</li>
	{/each}
</ul>

{#each tabs as item, i}
	{#if activeTabValue == i}
		<div class="box">
			<iframe class="frame" src="{item.url}" title="{item.title}"></iframe>
		</div>
	{/if}
{/each}

<style>
	h2 {
		text-align: center;
		margin: 0px;
		padding: 8px 10px 0px 10px;
	}

	.box {
		padding: 10px;
		border: 1px solid #eee;
		border-top: 0;
	}

	ul {
		display: flex;
		flex-wrap: wrap;
		height: 46px;
		padding-left: 0;
		margin-top: 0;
		margin-bottom: 0;
		list-style: none;
		border-bottom: 1px solid #eee;
	}

	span {
		display: block;
		color: #999999;
		padding: 12px 12px 8px;
		cursor: pointer;
		border-bottom: 3px solid transparent;
	}

	li.active > span {
		color: #333333;
		border-bottom: 3px solid black;
	}

	.frame {
		width: 100%;
		height: 100%;
		border: none;
	}
</style>
