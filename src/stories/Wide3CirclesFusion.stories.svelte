<script context="module">
	import Wide3CirclesFusion from '$lib/Buttons/Wide3CirclesFusion.svelte';

	export const meta = {
		title: 'Buttons/Special/Wide3CirclesFusion',
		component: Wide3CirclesFusion,
		tags: ['autodocs'],
		argTypes: {
			startText: { 
				control: 'text',
				description:"Button text at animation start"
			},
			textOverride:{
				control: 'boolean',
				description:"Should the text change at the end of the animation"
			},
			animationText:{ 
				control: 'text',
				description:"Button text at animation end. Only applies if overrideText is set to true"
		 	},
			animationTrigger: { 
				control: { type: 'select' },
				options: ['hover', 'click'],
				description:"Event which triggers the animation"
			 },
			fontColor: { 
				control: 'color',
				description:"The font color at the animation start."
			},
			fontAnimationColor: { 
				control: 'color',
				description:"The destination font color at the animation end."
			},
			fontSize: { control: 'text' },
			circlesColor: { 
				control: 'color',
				description:"The color of the animated circles." 
			},
			circlesSize: { 
				control: 'text',
				description:"The size of the animated circles. Enter valid css size values e.g. 200px." 
			},
			animationDuration: { 
				control: 'text',
				description:"Duration of the circles moving to the center. Enter a valid css time duration value e.g. 0.5s or 2s" 
			},
			animationDelay: { 
				control: 'text',
				description:"Time after the text and button background should start their animation. Only applies for animationTrigger = hover, Enter a valid css time duration value e.g. 0.5s or 2s" 
			},
			btnBackgroundColor: { 
				control: 'color',
				description:"The destination button background color at the animation end." 
			},
			btnWidth: { 
				control: 'text',
				description:"The button width. Enter valid css size values e.g. 200px, 30%, fit-content." 
			},
			btnHeight: { 
				control: 'text',
				description:"The button height. Enter valid css size values e.g. 200px, 30%, fit-content." 
			},
			areaWidth: { 
				control: 'text',
				description:"The width of the component. Enter valid css size values e.g. 200px, 100%, fit-content." 
			},
			areaHeight: { 
				control: 'text',
				description:"The height of the component. Enter valid css size values e.g. 200px, 30%, fit-content."
			},
			areaBackgroundColor: { 
				control: 'color',
				description:"The background color of the component area."
			},
		}
	};
</script>

<script>
	import { Story, Template } from '@storybook/addon-svelte-csf';
</script>

<Template let:args>
	<!--👇 'on:click' allows to forward event to addon-actions  -->
	<Wide3CirclesFusion {...args} />
</Template>

<Story name=Hover-Animation args={ { 
	startText:"SUBSCRIBE",
	animationDuration: "0.3s",
	animationDelay: "0.3s"
}}/>

<Story name=Click-Animation args={ { 
	animationDuration: "1.5s",
	animationTrigger: "click",
	fontColor: "#f55555",
	fontAnimationColor: "#b4edde",
	circlesColor: "#f55555",
	btnBackgroundColor: "#f55555",
	areaBackgroundColor: "#b4edde",
	startText:"BUY"
}}/>

<Story name=Text-Change-Click args={ { 
	animationDuration: "1.5s",
	animationTrigger: "click",
	fontColor: "#f55555",
	fontAnimationColor: "#b4edde",
	circlesColor: "#f55555",
	btnBackgroundColor: "#f55555",
	areaBackgroundColor: "#b4edde",
	textOverride: true
}}/>

<Story name=Text-Change-Hover args={ { 
	startText: "VIEW",
	animationText: "DETAILS",
	textOverride: true

}}/>
