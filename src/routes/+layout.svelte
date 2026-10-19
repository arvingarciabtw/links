<script lang="ts">
	import "../global.css";
	import favicon from "#lib/assets/favicon.png";
	import type { LayoutProps } from "./$types";

	let { children }: LayoutProps = $props();
</script>

<svelte:head>
	<link rel="icon" type="image/x-icon" href={favicon} />
</svelte:head>

<main>
	{@render children()}
</main>

<style>
	:global(h1) {
		margin-bottom: 2rem;
		padding: 0.25em 0.5em 0.125em;
		width: max-content;
		background: blue;
		color: white;
		font-size: 0.875rem;
		font-weight: 400;
	}

	:global(ul) {
		padding: 0;
		list-style-type: none;
		display: flex;
		flex-direction: column-reverse;
		gap: 0.5rem;
	}

	:global(li) {
		line-height: 1.75;
		&::before {
			content: "* ";
		}
	}

	:global(a) {
		color: blue;

		&:hover {
			text-decoration-style: dotted;
		}
	}

	:global(code) {
		padding: 0.125em 0.375em;
		background: ghostwhite;
		border: 1px dotted gainsboro;
		font-weight: 400;
	}

	@media (max-width: 800px) {
		:global(ul) {
			gap: 1.5rem;
		}
	}

	@media (max-width: 500px) {
		:global(h1) {
			font-size: 0.75rem;
		}
	}
</style>
