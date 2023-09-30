<script lang="ts">
	let href = '';
	let className = '';
	export { className as class };
	export let style = '';
	export let color = 'black';
	export let animationBackgroundColor = 'violet';
	export let animationDuration = '0.7s';
	export let overrideContent = false;
	export let backgroundColor = '';
	export let animationColor = 'white';
	export let animationContent = '';
    let translateX = '';
    let translateY = '';
    export let direction = 'left';
    $: switch (direction){
        case 'left':
            translateX = '-100%';
            translateY = '0';  
            break; 
        case 'right':
            translateX = '100%';
            translateY = '0';
            break; 
        case 'top':
            translateY = '-100%';
            translateX = '0'; 
            break;   
        case 'bottom':
            translateY = '100%';
            translateX = '0';  
            break; 
    
    };


</script>

<div class="">
	<a
		{href}
		class={className}
		style="--translateX:{translateX}; --translateY:{translateY}; --color:{color}; --animationColor:{animationColor}; --animationBackgroundColor:{animationBackgroundColor}; --animationDuration:{animationDuration}; {overrideContent
			? `--backgroundColor:${backgroundColor}; --content:"${animationContent}"; --zIndex:0;`
			: `--content:""; --zIndex:-1;`} {style}"
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
		transition: color var(--animationDuration);
		&:before {

			content: var(--content);
			position: absolute;
			left: 0;
			top: 0;
			height: 100%;
			width: 100%;
            transform: translate(var(--translateX), var(--translateY));
			
          

			background-color: var(--animationBackgroundColor);
			z-index: var(--zIndex);
			transition: transform var(--animationDuration);
			display: flex;
			justify-content: center;
			align-items: center;
			flex-wrap: wrap;
			flex-direction: column;
		}
		&:hover {
			color: var(--animationColor);
		}

		&:hover:before {
            transform: translate(0, 0);            
		}
	}
</style>
