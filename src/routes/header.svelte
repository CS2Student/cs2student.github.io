<script lang="ts">
	import * as config from '$lib/config';
	import Toggle from './toggle.svelte';
</script>

<nav class="header">
	<ul class="links">
		<li>
			<a href="/" class="title link">
				<b>{config.title}</b>
			</a>
		</li>
		<li>
			<a href="/about" class="link">About</a>
		</li>
		<li>
			<a href="https://github.com/CS2Student" class="link">Github</a>
		</li>
		<li>
			<Toggle />
		</li>
	</ul>
</nav>

<style>
	.header {
		display: flex;
		justify-content: center;
		padding-block: var(--size-7);
	}
	nav {
		padding-block: var(--size-7);
	}

	.links {
		margin-block: var(--size-7);
	}

	.link {
		text-decoration: underline;
		text-decoration-color: transparent;
		transition: text-decoration-color 0.3s ease;
	}

	.link:hover {
		text-decoration-color: var(--text-1-light);
	}

	a {
		color: var(--text-1);
		text-decoration: none;
	}

	@media (min-width: 768px) {
		nav {
			display: flex;
			justify-content: space-between;
		}

		.links {
			display: flex;
			gap: var(--size-7);
			margin-block: 0;
		}
	}
</style>
