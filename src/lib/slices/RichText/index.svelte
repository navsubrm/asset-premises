<script lang="ts">
	import type { Content } from '@prismicio/client';
	import { PrismicRichText } from '@prismicio/svelte';
	import Label from './Label.svelte';

	export let slice: Content.RichTextSlice;
</script>

<section class:dark-mode={false}>
	<div class="container">
		<PrismicRichText
			field={slice.primary.content}
			components={{
				label: Label
			}}
		/>
	</div>
</section>

<style>
	section {
		background-color: var(--white);
	}
	.container {
		max-width: 600px;
		margin: 6em auto;
		padding: 3em;
	}
</style>
