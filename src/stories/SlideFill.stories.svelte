<script context="module">
  import SlideFill from '$lib/Buttons/SlideFill.svelte';

  export const meta = {
    
    title: 'Buttons/Fill/SlideFill',
    component: SlideFill,
    tags: ['autodocs'],
    argTypes: {
    color: { control: 'color' },
    animationColor: { 
      control: 'color',
      description:"Only applies if overrideContent is set to true" },
    animationBackgroundColor: { control: 'color' },
    overrideContent:{ control: 'boolean'},
    backgroundColor: { 
      control: 'color',
      description:"Only applies if overrideContent is set to true" },
    animationContent: {control: 'text'},
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
  <SlideFill {...args}>
    {#if args.slot}
      {args.slot}
      {:else}
  Hover me
  {/if}

   
  </SlideFill>
</Template>
<Story name="Left">
  <SlideFill direction='left'>Left Fill</SlideFill>
</Story>

<Story name="Right">
  <SlideFill direction='right'>Right Fill</SlideFill>
</Story>

<Story name="Top">
  <SlideFill direction='top'>Top Fill</SlideFill>
</Story>

<Story name="Bottom">
  <SlideFill direction='bottom'>Bottom Fill</SlideFill>
</Story>

<Story name="Override">
<SlideFill animationDuration="0.6s" overrideContent=true backgroundColor="black" color="red", animationColor="blue" animationContent="Vote for Biden" animationBackgroundColor="#fff200">
  Vote for Trump
</SlideFill>
</Story>

<Story name="Button No Args">
  <SlideFill></SlideFill>
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


