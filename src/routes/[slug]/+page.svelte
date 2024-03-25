<script lang="ts">
	import { formatDate } from '$lib/utils';

	export let data;
</script>

<svelte:head>
	<title>{data.meta.title}</title>
	<meta property="og:type" content="article" />
	<meta property="og:title" content={data.meta.title} />
</svelte:head>

<article>
	<hgroup>
		<h2>{data.meta.title}</h2>
		<p>{formatDate(data.meta.date)}</p>
	</hgroup>

	<div class="tags">
		{#each data.meta.categories as category}
			<span class="tag surface-4">&num;{category}</span>
		{/each}
	</div>

	<div class="prose">
		<svelte:component this={data.content} />
	</div>
</article>

<style>
	article {
		max-inline-size: var(--size-content-3);
		margin-inline: auto;
		box-shadow: var(--shadow-2);
		border-radius: var(--radius-1);
		padding: var(--size-fluid-3);
		background-color: #fffbcc;
		color: var(--text-1-light);
	}

	h2 {
		text-transform: capitalize;
		color: var(--text-1-light);
	}

	h2 + p {
		margin-top: var(--size-2);
		color: var(--text-2-light);
	}

	.tags {
		display: flex;
		flex-wrap: wrap;
		gap: var(--size-3);
		margin-top: var(--size-7);
	}

	.tag {
		padding: var(--size-2) var(--size-3);
		border-radius: var(--radius-2);
		white-space: nowrap;
		overflow: hidden;
		text-overflow: ellipsis;
	}
</style>
