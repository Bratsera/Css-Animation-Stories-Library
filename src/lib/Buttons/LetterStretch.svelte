<script lang="ts">
	let href = '';
	let className = '';
	export { className as class };
	export let style = '';
	export let startColor = 'black';
	export let endColor = 'black';
	export let startBackgroundColor = 'transparent';
	export let endBackgroundColor = 'transparent';
	export let animationDuration = '0.5s';
	export let startLetterSpacing = '-2px';
	export let endLetterSpacing = '5px';
	export let startFontSize = '45px';
	export let endFontSize = '55px';
	export let startFontWeight = 300;
	export let endFontWeight = 900;

	export let width = '300px';
	export let height = '120px';



</script>

<div style:width style:height class="">
	<a
		{href}
		class={className}
		style="--fontWeight:{startFontWeight}; --endFontWeight:{endFontWeight}; --fontSize:{startFontSize}; --endFontSize:{endFontSize}; --letterSpacing:{startLetterSpacing}; --endLetterSpacing:{endLetterSpacing}; --backgroundColor:{startBackgroundColor}; --color:{startColor}; --endColor:{endColor}; --endBackgroundColor:{endBackgroundColor}; --animationDuration:{animationDuration};"
	>
		<slot>Submit</slot>
	</a>
</div>

<style lang="less">
	a {
		text-decoration: none;
		color: var(--color);
		font-family: 'roboto';
		letter-spacing: var(--letterSpacing);
		font-size: var(--fontSize);
		font-weight: 300;
		border: 3px solid var(--color);
		display: flex;
		justify-content: center;
		align-items: center;
		width: 100%;
		height: 100%;

		position: relative;
		overflow: hidden;
		background-color: var(--backgroundColor);
		transition: all var(--animationDuration);
		&:hover {
			background-color: var(--endBackgroundColor);
			font-size: var(--endFontSize);
			color: var(--endColor);
			letter-spacing: var(--endLetterSpacing);
			border: 5px solid var(--endColor);
		}
	}
</style>
