<script context="module">
	import Swaping from '$lib/Buttons/Swaping.svelte';

	export const meta = {
		title: 'Buttons/Swaping',
		component: Swaping,
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
	<Swaping {...args} />
</Template>
<Story name=customize/>
<Story name=" default in:left-bottom to out: right-top">
	<Swaping/>
</Story>
<Story name=" in:left-top to out: right-bottom">
	<Swaping swapInDirection='left-top' swapOutDirection='right-bottom' />
</Story>

<Story name=" in:left-bottom to out: right-bottom">
	<Swaping swapInDirection='left-bottom' swapOutDirection='right-bottom'/>
</Story>

<Story name=" in:left-top to out: right-top">
	<Swaping swapInDirection='left-top' swapOutDirection='right-top'/>
</Story>

<Story name=" in:left-bottom to out: left-top">
	<Swaping swapInDirection='left-bottom' swapOutDirection='left-top'/>
</Story>

<Story name=" in:left-top to out: left-bottom">
	<Swaping swapInDirection='left-top' swapOutDirection='left-bottom'/>
</Story>

<Story name=" in:left-bottom to out: left-bottom">
	<Swaping swapInDirection='left-bottom' swapOutDirection='left-bottom'/>
</Story>

<Story name=" in:left-top to out: left-top">
	<Swaping swapInDirection='left-top' swapOutDirection='left-top'/>
</Story>

<Story name=" in:right-bottom to out: left-top">
	<Swaping swapInDirection='right-bottom' swapOutDirection='left-top'/>
</Story>

<Story name=" in:right-top to out: left-bottom">
	<Swaping swapInDirection='right-top' swapOutDirection='left-bottom'/>
</Story>

<Story name=" in:right-bottom to out: left-bottom">
	<Swaping swapInDirection='right-bottom' swapOutDirection='left-bottom'/>
</Story>

<Story name=" in:right-top to out: left-top">
	<Swaping swapInDirection='right-top' swapOutDirection='left-top'/>
</Story>

<Story name=" in:right-bottom to out: right-top">
	<Swaping swapInDirection='right-bottom' swapOutDirection='right-top'/>
</Story>

<Story name=" in:right-top to out: right-bottom">
	<Swaping swapInDirection='right-top' swapOutDirection='right-bottom'/>
</Story>

<Story name=" in:right-bottom to out: right-bottom">
	<Swaping swapInDirection='right-bottom' swapOutDirection='right-bottom'/>
</Story>

<Story name=" in:right-top to out: right-top">
	<Swaping swapInDirection='right-top' swapOutDirection='right-top'/>
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
