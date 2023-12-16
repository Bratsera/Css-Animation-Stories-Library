<script context="module">
  import SlideRoundedFill from '$lib/Buttons/SlideRoundedFill.svelte';

  export const meta = {
    
    title: 'Buttons/SlideRoundedFill',
    component: SlideRoundedFill,
    tags: ['autodocs'],
    argTypes: {
    color: { control: 'color' },
    animationColor: { control: 'color' },
    animationBackgroundColor: { control: 'color' },
    slot: {control: 'text'},
    direction:{
      control: { type: 'select' },
      options: ['left', 'right', 'top', 'bottom'],
    }
    } 
  }
</script>

<script>
  import { Story, Template } from '@storybook/addon-svelte-csf';

</script>
<Template let:args>
  <!--👇 'on:click' allows to forward event to addon-actions  -->
  <SlideRoundedFill {...args}>
    {#if args.slot}
      {args.slot}
      {:else}
  Hover me
  {/if}

   
  </SlideRoundedFill>
</Template>
<Story name="Customize"/>
<Story name="Left">
  <SlideRoundedFill direction='left'>Left Fill</SlideRoundedFill>
</Story>

<Story name="Right">
  <SlideRoundedFill direction='right'>Right Fill</SlideRoundedFill>
</Story>

<Story name="Top">
  <SlideRoundedFill direction='top'>Top Fill</SlideRoundedFill>
</Story>

<Story name="Bottom">
  <SlideRoundedFill direction='bottom'>Bottom Fill</SlideRoundedFill>
</Story>


<Story name="Button No Args">
  <SlideRoundedFill></SlideRoundedFill>
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


