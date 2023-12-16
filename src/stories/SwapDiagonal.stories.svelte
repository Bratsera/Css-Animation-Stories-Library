<script context="module">
	import SwapDiagonal from '$lib/Buttons/SwapDiagonal.svelte';

	export const meta = {
		title: 'Buttons/Swap/SwapDiagonal',
		component: SwapDiagonal,
		tags: ['autodocs'],
		argTypes: {
			color: { control: 'color' },
			animationBackgroundColor: { control: 'color' },
			backgroundColor: { control: 'color' },
			animationDuration: { control: 'text' },
			swapInDirection: {
				options: [0, 1, 2, 3], // iterator
				mapping: [0, 1, 2, 3], // values
				control: {
					type: 'select',
					labels: ['left bottom', 'left top', 'right bottom', 'right top']
				}
			},
			swapOutDirection: {
				options: [0, 1, 2, 3], // iterator
				mapping: [0, 1, 2, 3], // values
				control: {
					type: 'select',
					labels: ['left bottom', 'left top', 'right bottom', 'right top']
				}
			}
		}
	};
</script>

<script>
	import { Story, Template } from '@storybook/addon-svelte-csf';
</script>

<Template let:args>
	<!--👇 'on:click' allows to forward event to addon-actions  -->
	<SwapDiagonal {...args} />
</Template>
<Story name=customize/>
<Story name=" default in:left-bottom to out: right-top">
	<SwapDiagonal/>
</Story>
<Story name=" in:left-top to out: right-bottom">
	<SwapDiagonal swapInDirection='left-top' swapOutDirection='right-bottom' />
</Story>

<Story name=" in:left-bottom to out: right-bottom">
	<SwapDiagonal swapInDirection='left-bottom' swapOutDirection='right-bottom'/>
</Story>

<Story name=" in:left-top to out: right-top">
	<SwapDiagonal swapInDirection='left-top' swapOutDirection='right-top'/>
</Story>

<Story name=" in:left-bottom to out: left-top">
	<SwapDiagonal swapInDirection='left-bottom' swapOutDirection='left-top'/>
</Story>

<Story name=" in:left-top to out: left-bottom">
	<SwapDiagonal swapInDirection='left-top' swapOutDirection='left-bottom'/>
</Story>

<Story name=" in:left-bottom to out: left-bottom">
	<SwapDiagonal swapInDirection='left-bottom' swapOutDirection='left-bottom'/>
</Story>

<Story name=" in:left-top to out: left-top">
	<SwapDiagonal swapInDirection='left-top' swapOutDirection='left-top'/>
</Story>

<Story name=" in:right-bottom to out: left-top">
	<SwapDiagonal swapInDirection='right-bottom' swapOutDirection='left-top'/>
</Story>

<Story name=" in:right-top to out: left-bottom">
	<SwapDiagonal swapInDirection='right-top' swapOutDirection='left-bottom'/>
</Story>

<Story name=" in:right-bottom to out: left-bottom">
	<SwapDiagonal swapInDirection='right-bottom' swapOutDirection='left-bottom'/>
</Story>

<Story name=" in:right-top to out: left-top">
	<SwapDiagonal swapInDirection='right-top' swapOutDirection='left-top'/>
</Story>

<Story name=" in:right-bottom to out: right-top">
	<SwapDiagonal swapInDirection='right-bottom' swapOutDirection='right-top'/>
</Story>

<Story name=" in:right-top to out: right-bottom">
	<SwapDiagonal swapInDirection='right-top' swapOutDirection='right-bottom'/>
</Story>

<Story name=" in:right-bottom to out: right-bottom">
	<SwapDiagonal swapInDirection='right-bottom' swapOutDirection='right-bottom'/>
</Story>

<Story name=" in:right-top to out: right-top">
	<SwapDiagonal swapInDirection='right-top' swapOutDirection='right-top'/>
</Story>
<!--

<Story name="" let:slot>
  <AnimatedButton animationDuration="0.4s" animationBackgroundColor="#fff200" >
    {#if slot}
    {slot}
    {:else}
    Hover me
    {/if}
  </AnimatedButton>
  </Story>

-->
