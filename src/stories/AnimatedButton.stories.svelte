<script context="module">
  import AnimatedButton from '$lib/Buttons/AnimatedButton.svelte';

  export const meta = {
    
    title: 'Animated/Button',
    component: AnimatedButton,
    tags: ['autodocs'],
    argTypes: {
    "backgroundColor": { control: 'color' },
    "--animationBackgroundColor": { control: 'color' },
    "color": { control: 'color' }
    } 
  }
</script>

<script>
  import { Story, Template } from '@storybook/addon-svelte-csf';

</script>
<Template let:args>
  <!--👇 'on:click' allows to forward event to addon-actions  -->
  <AnimatedButton {...args}>
    {#if args.slot}
      {args.slot}
    {/if}
   
  </AnimatedButton>
</Template>

<Story name="Rounded" args={{slot: "Hi", "animationDuration": `1s`, "animationBackgroundColor":"#fff200"}}/>

<Story name="Square" source args={{'--animationBackgroundColor':"#fff200"}}/>

<!-- Dynamic snippet should be disabled for this story -->
<Story name="Button No Args">
  <AnimatedButton>Label</AnimatedButton>
</Story>


