<script lang="ts">
	let href = '';
	let className = '';
	export { className as class };
	export let style = '';
	export let color = 'tomato';
	export let animationBackgroundColor = 'tomato';
	export let animationDuration = '0.7s';
	export let animationColor = 'white';

    export let direction = 'bottom';

	let borderTopLeft = '';
	let borderTopRight = '';
	let borderBottomRight = '';
	let borderBottomLeft = '';
	let height = '';
	let width = '';
	let heightAfter = '';
	let widthAfter = '';
	let top = '';
	let bottom = '';
	let left = '';
	let right = '';

    $: switch (direction){
        case 'left':
			borderTopLeft ='50%'
			borderTopRight = '0';
			borderBottomRight = '0';
			borderBottomLeft = '50%';
			height = '100%';
			width = '0';
			heightAfter = '100%';
			widthAfter = '200%'; 
			top = '0';
			right = '0';
            break; 
        case 'right':
			borderTopLeft = '0';
			borderTopRight = '50%';
			borderBottomRight = '50%';
			borderBottomLeft = '0';
			height = '100%';
			width = '0';
			heightAfter = '100%';
			widthAfter = '200%'; 
			top = '0';
			left = '0';
            break; 
        case 'bottom':
			borderTopLeft = '0';
			borderTopRight = '0';
			borderBottomRight = '50%';
			borderBottomLeft = '50%';
			height = '0';
			width = '100%';
			heightAfter = '200%';
			widthAfter = '100%'; 
			top = '0';
			left = '0';
            break;   
        case 'top':
			borderTopLeft = '50%';
			borderTopRight = '50%';
			borderBottomRight = '0';
			borderBottomLeft = '0';
			height = '0';
			width = '100%';
			heightAfter = '200%';
			widthAfter = '100%'; 
			bottom = '0';
			left = '0';
            break; 
    
    };


</script>

<div class="">
	<a
		{href}
		class={className}
		style="--borderTopLeft:{borderTopLeft}; --borderTopRight:{borderTopRight}; --borderBottomRight:{borderBottomRight}; --borderBottomLeft:{borderBottomLeft}; --height:{height}; --heightAfter:{heightAfter}; --width:{width}; --widthAfter:{widthAfter}; --top:{top}; --left:{left}; --bottom:{bottom}; --right:{right};  --color:{color}; --animationColor:{animationColor}; --animationBackgroundColor:{animationBackgroundColor}; --animationDuration:{animationDuration};
		{style}"
	>
		<slot>Submit</slot>
	</a>
</div>

<style lang="less">
	a {
		display: inline-block;
		text-decoration: none;
		color: var(--color);
		border-color: var(--color);
		font-family: sans-serif;
		font-size: 45px;
		border: 5px solid;
		padding: 40px 80px;
		position: relative;
		overflow: hidden;
		transition: all var(--animationDuration);
		z-index: 1;
		&:before {

			content: '';
			position: absolute;
			left: var(--left);
			top: var(--top);
			bottom: var(--bottom);
			right: var(--right);
			border-radius: var(--borderTopLeft) var(--borderTopRight) var(--borderBottomRight) var(--borderBottomLeft);
			height: var(--height);
			width: var(--width);
			color: var(--backgroundColor);


			background-color: var(--animationBackgroundColor);

			transition: all var(--animationDuration);
			display: flex;
			justify-content: center;
			align-items: center;
			flex-wrap: wrap;
			flex-direction: column;
			z-index: -1;
		}
		&:hover {
			color: var(--animationColor);
			border-color: var(--animationBackgroundColor);
		}

		&:hover:before {
			height: var(--heightAfter);
			width: var(--widthAfter);
		   	color: var(--animationColor);
		}
	}
</style>
