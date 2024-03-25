<script lang="ts">
	import { formatDate } from '$lib/utils';
	import * as config from '$lib/config';
	export let data;
</script>

<svelte:head>
	<title>{config.title}</title>
</svelte:head>

<section>
	<ul class="posts">
		{#each data.posts as post}
			<li class="post">
				<a href={post.slug} class="title">{post.title}</a>
				<p class="date">{formatDate(post.date)}</p>
				<p class="description">{post.description}</p>
			</li>
		{/each}
	</ul>
</section>

<style>
	section {
		display: flex;
		justify-content: center;
		min-height: 10vh;
	}
	.posts {
		display: grid;
		gap: var(--size-1);
	}

	.post {
		max-inline-size: var(--size-content-3);
		border-radius: var(--radius-1);
		width: 290px;
		padding: var(--size-fluid-3);
		box-shadow: var(--shadow-2);
		background-color: #fffbcc;
		&:hover {
			box-shadow: var(--shadow-3);
		}
	}

	.post:not(:last-child) {
		border-bottom: 1px solid var(--border);
		padding-bottom: var(--size-7);
	}

	.title {
		font-size: var(--font-size-fluid-0);
		text-transform: capitalize;
		color: var(--text-1-light);
		text-decoration: underline;
		text-decoration-color: transparent;
		transition: text-decoration-color 0.3s ease;
	}

	.title:hover {
		text-decoration-color: var(--text-1-light);
	}

	.date {
		color: var(--text-2-light);
	}

	.description {
		margin-top: var(--size-1);
		color: var(--text-2-light);
	}
</style>
