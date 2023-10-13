<script lang="ts">
	enum SwapDirection {
		'left-bottom',
		'left-top',
		'right-bottom',
		'right-top'
	}
	let href = '';
	let className = '';
	export { className as class };
	export let style = '';
	export let color = 'black';
	export let animationBackgroundColor = 'black';
	export let animationDuration = '0.4s';
	export let backgroundColor = 'yellow';
	export let buttonText = "Swap it like it's hot";
	export let swapInDirection: string  = SwapDirection[SwapDirection["left-bottom"]];
	export let swapOutDirection: string = SwapDirection[SwapDirection["right-top"]];

	let translateXIn = '0';
	let translateYIn = '0';
	let translateXOut = '0';
	let translateYOut = '0';

	$: switch (swapInDirection) {
		case SwapDirection[SwapDirection["left-bottom"]]:
			translateXIn = '-100%';
			translateYIn = '100%';
			break;
		case SwapDirection[SwapDirection["left-top"]]:
			translateXIn = '-100%';
			translateYIn = '-100%';
			break;
		case SwapDirection[SwapDirection["right-bottom"]]:
			translateXIn = '100%';
			translateYIn = '100%';
			break;
		case SwapDirection[SwapDirection["right-top"]]:
			translateXIn = '100%';
			translateYIn = '-100%';
			break;
	}
	$: switch (swapOutDirection) {
		case SwapDirection[SwapDirection["left-bottom"]]:
			translateXOut = '-100%';
			translateYOut = '100%';
			break;
		case SwapDirection[SwapDirection["left-top"]]:
			translateXOut = '-100%';
			translateYOut = '-100%';
			break;
		case SwapDirection[SwapDirection["right-bottom"]]:
			translateXOut = '100%';
			translateYOut = '100%';
			break;
		case SwapDirection[SwapDirection["right-top"]]:
			translateXOut = '100%';
			translateYOut = '-100%';
			break;
	}
</script>

<div class="">
	<a
		{href}
		class={className}
		style='--content:"{buttonText}"; --translateXIn:{translateXIn}; --translateYIn:{translateYIn}; --translateXOut:{translateXOut}; --translateYOut:{translateYOut}; --backgroundColor:{backgroundColor}; --color:{color}; --animationBackgroundColor:{animationBackgroundColor}; --animationDuration:{animationDuration}; {style}'
		>{buttonText}
	</a>
</div>

<style lang="less">
	a {
		display: inline-block;
		text-decoration: none;
		color: transparent;
		padding: 20px 40px;
		position: relative;
		overflow: hidden;
		background-color: var(--animationBackgroundColor);

		&:before {
			width: 100%;
			height: 100%;
			color: var(--color);
			content: var(--content);
			position: absolute;
			left: 0;
			top: 0;
			transform: translate(var(--translateXIn), var(--translateYIn));
			background-color: var(--backgroundColor);
			transition: transform var(--animationDuration);
			display: flex;
			justify-content: center;
			align-items: center;
			flex-wrap: wrap;
			flex-direction: column;
		}

		&:hover:before {
			transform: translate(0, 0);
		}
		&:after {
			width: 100%;
			height: 100%;
			color: var(--color);
			content: var(--content);
			position: absolute;
			left: 0;
			top: 0;
			transform: translate(0, 0);
			background-color: var(--backgroundColor);
			transition: transform var(--animationDuration);
			display: flex;
			justify-content: center;
			align-items: center;
			flex-wrap: wrap;
			flex-direction: column;
		}
		&:hover:after {
			transform: translate(var(--translateXOut), var(--translateYOut));
		}
	}
</style>
