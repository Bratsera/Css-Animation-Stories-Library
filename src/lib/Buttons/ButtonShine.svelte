<script lang="ts">
	let href = '';
	let className = '';
	export { className as class };
	export let style = '';
	export let color = 'white';
	export let animationBackgroundColor = 'red';
	export let animationDuration = '0.7s';
	export let shineDuration = '0.4s';
	export let backgroundColor = 'black';
	export let animationColor = 'black';


</script>

<div class="">
	<a
		{href}
		class={className}
		style="--shineDuration: {shineDuration}; --backgroundColor:{backgroundColor}; --color:{color}; --animationColor:{animationColor}; --animationBackgroundColor:{animationBackgroundColor}; --animationDuration:{animationDuration};"
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
		letter-spacing: 3px;
		font-size: 45px;
		font-weight: bold;
		border: 5px solid var(--color);
		padding: 40px 80px;
		position: relative;
		overflow: hidden;
		background-color: var(--backgroundColor);
		transition: background-color var(--animationDuration);
		&:before {

			content: "";
			position: absolute;
			left: 0;
			top: 50%;
			height: 30px;
			width: 100%;
			transform: translateX(-100%) rotate(45deg);
			background-color: white;
			transition: transform var(--shineDuration);
		}
		&:hover {
			background-color: var(--animationBackgroundColor);
			color: var(--animationColor);
		}

		&:hover:before {
            transform: translateX(100%) rotate(45deg);            
		}
	}
</style>
