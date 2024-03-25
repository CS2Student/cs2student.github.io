<script lang="ts">
	import { page } from '$app/stores';
</script>

<div class="error">
	<h2>{$page.status} : {$page.error?.message}</h2>
</div>

<style>
	.error {
		height: 100%;
		display: grid;
		place-content: center;
	}
</style>
