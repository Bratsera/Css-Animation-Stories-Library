<script context="module">
	import ButtonShine from '$lib/Buttons/ButtonShine.svelte';

	export const meta = {
		title: 'Buttons/ButtonShine',
		component: ButtonShine,
		tags: ['autodocs'],
		argTypes: {
			color: { control: 'color' },
			animationColor: { control: 'color' },
			animationBackgroundColor: { control: 'color' },
			backgroundColor: { control: 'color' },
      animationDuration: {control: 'text'}
    }
  }
</script>

<script>
	import { Story, Template } from '@storybook/addon-svelte-csf';
</script>

<Template let:args>
	<!--👇 'on:click' allows to forward event to addon-actions  -->
	<ButtonShine {...args}>
		{#if args.slot}
			{args.slot}
		{:else}
			Hover me
		{/if}
	</ButtonShine>
</Template>
<Story name="Left">
	<ButtonShine>Left Fill</ButtonShine>
</Story>

<Story name="Right">
	<ButtonShine>Right Fill</ButtonShine>
</Story>

<Story name="Button No Args">
	<ButtonShine />
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
