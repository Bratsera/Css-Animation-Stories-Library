<script context="module">
  import SlideAll from '$lib/Buttons/SlideAll.svelte';

  export const meta = {
    
    title: 'SlideAll/Button',
    component: SlideAll,
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
      options: ['in', 'out'],
    }
    } 
  }
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
<Story name="Left">
  <SlideAll direction='left'>Left Fill</SlideAll>
</Story>

<Story name="Right">
  <SlideAll direction='right'>Right Fill</SlideAll>
</Story>

<Story name="Top">
  <SlideAll direction='top'>Top Fill</SlideAll>
</Story>

<Story name="Bottom">
  <SlideAll direction='bottom'>Bottom Fill</SlideAll>
</Story>

<Story name="Override">
<SlideAll animationDuration="0.6s" overrideContent=true backgroundColor="black" color="red", animationColor="blue" animationContent="Vote for Biden" animationBackgroundColor="#fff200">
  Vote for Trump
</SlideAll>
</Story>

<Story name="Button No Args">
  <SlideAll></SlideAll>
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


