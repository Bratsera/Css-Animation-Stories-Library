<script context="module">
	import SlideAll from '$lib/Buttons/SlideAll.svelte';

	export const meta = {
		title: 'Buttons/SlideAll',
		component: SlideAll,
		tags: ['autodocs'],
		argTypes: {
			color: { control: 'color' },
			animationColor: {
				control: 'color'
			},
			animationBackgroundColor: { control: 'color' },
			backgroundColor: {
				control: 'color'
			},
			slot: { control: 'text' },
			direction: {
				control: { type: 'select' },
				options: ['in', 'out']
			}
		}
	};
</script>

<script>
	import { Story, Template } from '@storybook/addon-svelte-csf';
</script>

<Template let:args>
	<!--👇 'on:click' allows to forward event to addon-actions  -->
	<SlideAll {...args}>
		{#if args.slot}
			{args.slot}
		{:else}
			Hover me
		{/if}
	</SlideAll>
</Template>
<Story name="Customize Text"/>

<Story name="In to Out">
	<SlideAll>In to Out</SlideAll>
</Story>

<Story name="Out to In">
	<SlideAll direction="out" color="white" animationColor="black">Out to In</SlideAll>
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
