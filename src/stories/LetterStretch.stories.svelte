<script context="module">
	import LetterStretch from '$lib/Buttons/LetterStretch.svelte';

	export const meta = {
		title: 'Buttons/LetterAnimation/LetterStretch',
		component: LetterStretch,
		tags: ['autodocs'],
		argTypes: {
			startColor: { control: 'color' },
			endColor: { control: 'color' },
			startBackgroundColor: { control: 'color' },
			endBackgroundColor: { control: 'color' },
			slot: { control: 'text' },
		}
	};
</script>

<script>
	import { Story, Template } from '@storybook/addon-svelte-csf';
</script>

<Template let:args>
	<!--👇 'on:click' allows to forward event to addon-actions  -->
	<LetterStretch {...args}>
		{#if args.slot}
			{args.slot}
		{:else}
			Hover me
		{/if}
	</LetterStretch>
</Template>
<Story name="Customize Text"/>

<Story name="Small">
	<LetterStretch height='100px' width='150px' >Small</LetterStretch>
</Story>
<Story name="Red to violet">
	<LetterStretch startColor='#fa2727' endColor='#6720ce' endLetterSpacing='0px' endFontWeight=300 endFontSize='45px'>Color change</LetterStretch>
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
