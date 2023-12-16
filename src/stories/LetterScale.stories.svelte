<script context="module">
	import LetterScale from '$lib/Buttons/LetterScale.svelte';

	export const meta = {
		title: 'Buttons/LetterAnimation/LetterScale',
		component: LetterScale,
		tags: ['autodocs'],
		argTypes: {
			startColor: { control: 'color' },
			endColor: { control: 'color' },
			startBackgroundColor: { control: 'color' },
			endBackgroundColor: { control: 'color' },
			label: { control: 'text' },
			startBorderColor: {control: 'color'},
			endBorderColor: {control: 'color'},
			direction: {
				control: {type: 'select'},
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
	<LetterScale {...args}>
	</LetterScale>
</Template>
<Story name="Default direction in"/>

<Story name="Direction out" args={ {direction:'out'}}>
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
