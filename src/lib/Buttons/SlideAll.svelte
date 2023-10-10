<script lang="ts">
	export let href: string = '';
	let className = '';
	export { className as class };
	export let style: string = '';
	export let color: string = 'black';
	export let animationBackgroundColor: string = 'black';
	export let animationDuration: string = '0.7s';
	export let backgroundColor: string = '';
	export let animationColor: string = 'white';
// div wrapper für normal background, animated back zIndex -1 und a tag color z index0
	let start = '';
	let finish = '';

	export let direction = 'in';
	$: switch (direction) {
		case 'in':
			start = '90deg';
			finish = '0';
			break;
		case 'out':
			start = '0';
			finish = '90deg';
			break;
	}
</script>

<div class="">
	<a
		{href}
		class={className}
		style="--backgroundColor:{backgroundColor}; --color:{color}; --start:{start}; --finish:{finish}; --animationColor:{animationColor}; --animationBackgroundColor:{animationBackgroundColor}; --animationDuration:{animationDuration}; {style}"
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
		&:hover{
			color: var(--animationColor);
			
		}
		&:before {
			content: "";
			position: absolute;
			left: 0;
			top: 0;
			height: 100%;
			width: 100%;
			transform: rotateX(var(--start));

			color: var(--animationColor);
			background-color: var(--animationBackgroundColor);
			z-index: -1;
			transition: transform var(--animationDuration);
			display: flex;
			justify-content: center;
			align-items: center;
			flex-wrap: wrap;
			flex-direction: column;
		}

		&:after {
			content: "";
			position: absolute;
			left: 0;
			top: 0;
			height: 100%;
			width: 100%;
			transform: rotateY(var(--start));

			color: var(--animationColor);
			background-color: var(--animationBackgroundColor);
			z-index: -1;
			transition: transform var(--animationDuration);
			display: flex;
			justify-content: center;
			align-items: center;
			flex-wrap: wrap;
			flex-direction: column;
		}
		&:hover:before {
			transform: rotateX(var(--finish));
		}
		&:hover:after {
			transform: rotateY(var(--finish));
		}
	}
</style>
