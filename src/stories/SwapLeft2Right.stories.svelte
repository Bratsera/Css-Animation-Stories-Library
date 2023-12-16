<script context="module">
	import SwapLeft2Right from '$lib/Buttons/SwapLeft2Right.svelte';

	export const meta = {
		title: 'Buttons/Swap/SwapLeft2Right',
		component: SwapLeft2Right,
		tags: ['autodocs'],
		argTypes: {
			color: { control: 'color' },
			centerBackgroundColor: { control: 'color' },
			backgroundColor: { control: 'color' },
			animationDuration: { control: 'text' },
		}
	};
</script>

<script>
	import { Story, Template } from '@storybook/addon-svelte-csf';
</script>

<Template let:args>
	<!--👇 'on:click' allows to forward event to addon-actions  -->
	<SwapLeft2Right {...args} />
</Template>

<Story name=customize/>



