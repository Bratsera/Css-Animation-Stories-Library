<script lang="ts">
	let href = '';
	let className = '';
	export { className as class };
	export let style = '';
	export let color = '#ff0';
	export let centerBackgroundColor = 'transparent';
	export let animationDuration = '0.4s';
	export let backgroundColor = '#363636';
	export let buttonText = "Swap it like it's hot";
	export let overflowHidden = true;

</script>

<div class="">
	<a
		{href}
		class={className}
		style='--content:"{buttonText}"; --overflowHidden:{overflowHidden ? "hidden" : "visible"}; --backgroundColor:{backgroundColor}; --color:{color}; --centerBackgroundColor:{centerBackgroundColor}; --animationDuration:{animationDuration}; {style}'
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
		overflow: var(--overflowHidden);
		background-color: var(--centerBackgroundColor);
		border: 3px solid var(--color);

		&:before {
			width: 100%;
			height: 100%;
			color: var(--color);
			content: var(--content);
			position: absolute;
			left: 0;
			top: 0;
			
			background-color: var(--backgroundColor);
			transition: var(--animationDuration);
			display: flex;
			justify-content: center;
			align-items: center;
			flex-wrap: wrap;
			flex-direction: column;
		}

		&:hover:before {
			left: 100%;
			transform: scale(0) rotateY(360deg);
		}
		&:after {
			width: 100%;
			height: 100%;
			color: var(--color);
			content: var(--content);
			position: absolute;
			left: -100%;
			top: 0;
			transform: scale(0) rotateY(0deg) ;
			background-color: var(--backgroundColor);
			transition: all var(--animationDuration);
			display: flex;
			justify-content: center;
			align-items: center;
			flex-wrap: wrap;
			flex-direction: column;
		}
		&:hover:after {
			left: 0;
			transform: scale(100%) rotateY(360deg) ;
			
		}
	}
</style>
