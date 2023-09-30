<script lang="ts">
	export let href: string = '';
	let className = '';
	export { className as class };
	export let style: string = '';
	export let color: string = '';
	export let animationBackgroundColor: string = '#fff200';
	export let animationDuration: string = '0.7s';
    export let overrideContent = false;
	export let backgroundColor: string = '';
	export let animationColor: string = '';
    export let animationContent= 'Hola';
    </script>

<div class="">
	<a {href} 
	class={className}
	style:color={color}
	style="--animationColor:{animationColor}; --animationBackgroundColor:{animationBackgroundColor}; --animationDuration:{animationDuration}; {overrideContent? `--backgroundColor:${backgroundColor}; --content:"${animationContent}"; --zIndex:0;` : `--content:""; --zIndex:-1;`} {style}"
>
		<slot>Submit</slot>
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
       overflow: hidden;
		background-color: var(--backgroundColor);
        &:before {

		transform-origin: bottom left;
		content: var(--content);
		position: absolute;
		left: 0;
		top: 0;
		height: 100%;
		width: 100%;
		transform: rotate(-90deg);
		color: var(--animationColor);
		background-color: var(--animationBackgroundColor);
		z-index: var(--zIndex);
		transition: transform var(--animationDuration);
        display: flex;
        justify-content: center;
        align-items: center;
		flex-wrap: wrap;
		flex-direction: column;
	}
	}
	
	a:hover:before {
        
		transform: rotate(0);
	}
</style>
