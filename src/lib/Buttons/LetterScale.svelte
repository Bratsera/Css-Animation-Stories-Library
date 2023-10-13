<script lang="ts">
	let href = '';
	let className = '';
	export { className as class };
	export let style = '';
	export let startColor = 'black';
	export let endColor = 'white';
	export let startBackgroundColor = 'transparent';
	export let endBackgroundColor = 'grey';
	export let animationDuration = '0.4s';
	export let label="Submit"
	export let direction = 'in';
	export let startBorderColor = startColor;
	export let endBorderColor = endBackgroundColor;
	let startScale = 5;
	let endScale = 1
	let startOpacity = 0;
	let endOpacity = 1;

	$: if(direction == 'in'){
		startScale = 5;
		endScale = 1;
		startOpacity = 0;
		endOpacity = 1;
	}
	$: if(direction == 'out'){
		startScale = 1;
		endScale = 5;
		startOpacity = 1;
		endOpacity = 0;
	}

</script>

	<a
		{href}
		class={className}
		style='--label:"{label}"; --borderColor:{startBorderColor}; --endBorderColor:{endBorderColor}; --opacity:{startOpacity}; --endOpacity:{endOpacity}; --startScale:{startScale}; --endScale:{endScale}; --backgroundColor:{startBackgroundColor}; --color:{startColor}; --endColor:{endColor}; --endBackgroundColor:{endBackgroundColor}; --animationDuration:{animationDuration}; {style}'
	>
		{label}
	</a>


<style lang="less">
	a {
		display: inline-block;
		position: relative;
		text-decoration: none;
		color: var(--color);
		border: 3px solid var(--borderColor);
		overflow: hidden;
		background-color: var(--backgroundColor);
		padding: 15px 20px;
		transition: border var(--animationDuration);
		&:before{
			content: var(--label);
			position: absolute;
			display: flex;
			justify-content: center;
			align-items: center;

			top: 0;
			left: 0;
			width: 100%;
			height: 100%;
			background-color: var(--endBackgroundColor);
			transform: scale(var(--startScale));
			opacity: var(--opacity);
			transition: all var(--animationDuration);
			color: var(--endColor);
		}
		&:hover:before{
			transform: scale(var(--endScale));
			opacity: var(--endOpacity);
		}
		&:hover{
			border: 3px solid var(--endBorderColor);
		}
	}
</style>
