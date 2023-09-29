<script lang="ts">
	import { onMount } from "svelte";

	export let href: string = '';
	let className = '';
	export { className as class };
	export let style: string = '';
	export let backgroundColor: string = '';
	export let animationBackgroundColor: string = '#fff200';
	export let animationDuration: string = '1s';
    export let overrideContent = false;
    export let animationContent= '1s';
    </script>

<div class="">
	<a {href} 
	class={className}
	style="--animationBackgroundColor:{animationBackgroundColor};  --backgroundColor:{backgroundColor}; --animationDuration:{animationDuration}; {style}"
>
		<slot>Hover Me</slot>
	</a>
</div>

<style lang="less">


	a {
		display: inline-block;
		text-decoration: none;
		color: var(--color);
		font-family: sans-serif;
		font-size: 45px;
		border: 5px solid #272727;
		padding: 40px 80px;
		position: relative;
       
		background-color: var(--backgroundColor);
        &:before {

		transform-origin: bottom left;
		content: 'Hi';
		position: absolute;
		left: 0;
		top: 0;
		height: 100%;
		width: 100%;
		transform: rotate(-90deg);
		background-color: var(--animationBackgroundColor);
		z-index: -1;
		transition: transform var(--animationDuration);
        display: flex;
        justify-content: center;
        align-items: center;
	}
	}
	
	a:hover:before {
        
		transform: rotate(0);
	}
</style>
