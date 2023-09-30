<script context="module">
  import RotateIn from '$lib/Buttons/RotateIn.svelte';

  export const meta = {
    
    title: 'RotateIn/Button',
    component: RotateIn,
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
    slot: {control: 'text'}
    } 
  }
</script>

<script>
  import { Story, Template } from '@storybook/addon-svelte-csf';

</script>
<Template let:args>
  <!--👇 'on:click' allows to forward event to addon-actions  -->
  <RotateIn {...args}>
    {#if args.slot}
      {args.slot}
      {:else}
  Hover me
  {/if}

   
  </RotateIn>
</Template>
<Story name="Normal" />

<Story name="Override">
<RotateIn animationDuration="0.1s" overrideContent=true backgroundColor="black" color="red", animationColor="blue" animationContent="Vote for Biden" animationBackgroundColor="#fff200">
  Vote for Trump
</RotateIn>
</Story>

<Story name="Button No Args">
  <RotateIn></RotateIn>
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


