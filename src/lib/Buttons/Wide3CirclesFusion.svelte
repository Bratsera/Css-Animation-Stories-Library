<script lang="ts">

	let href: string | undefined = undefined;
	let className = '';
	export let startText = 'DONATE';
	export let textOverride = false;
	export let animationText = 'THANK YOU!';
	export let animationTrigger = 'hover'
	export let fontColor = '#ff0';
	export let fontAnimationColor = 'grey';
	export let fontSize = '26px';
	export let circlesColor = '#ff0';
	export let circlesSize = '20px';
	export let animationDuration = '0.5s';
	export let animationDelay = '0.5s';
	export let btnWidth = '220px';
	export let btnHeight = '80px';
	export let btnBackgroundColor = '#ff0';
	export let areaWidth = '100%';
	export let areaHeight = 'fit-content';
	export let areaBackgroundColor = 'grey';
	export { className as class };
	export let style = '';


</script>

<div
	class="background"
	style="--areaHeight:{areaHeight}; --areaWidth:{areaWidth}; --areaBackgroundColor:{areaBackgroundColor};"
>
	<a 	tabindex="0"
		{href}
		class="{animationTrigger} {className}"
		style='--content:"{animationText}"; --circlesSize:{circlesSize}; --btnWidth:{btnWidth}; --fontAnimationColor:{fontAnimationColor}; 
			--btnHeight:{btnHeight}; --fontSize:{fontSize}; --circlesColor:{circlesColor}; --btnBackgroundColor:{btnBackgroundColor}; 
			--color:{fontColor}; --animationDuration:{animationDuration}; --animationDelay:{animationDelay}; {style}'
		><span class="btn-background"/>
		{#if textOverride}
		<span class="end-text" >
			{animationText}
		</span>
		<span class="start-text">
			{startText}
		</span>
		{:else}
			{startText}
		{/if}
	</a>
</div>

<style lang="less">
	@keyframes changeFontColor {
		0% {
			color: var(--color);
		}
		15% {
			color: var(--color);
		}
		30% {
			color: var(--fontAnimationColor);
		}

		70% {
			color: var(--fontAnimationColor);
		}
		85% {
			color: var(--color);
		}
		100% {
			color: var(--color);
		}
	}
	@keyframes circlesLeft {
		0% {
			left: 0;
			box-shadow: -100px 0 0 var(--circlesColor);
		}
		10% {
			left: 50%;
			box-shadow: 30px 0 0 var(--circlesColor);
			transform: translateX(-50%) translateY(-50%);
			opacity: 1;
		}
		90% {
			left: 50%;
			box-shadow: 30px 0 0 var(--circlesColor);
			transform: translateX(-50%) translateY(-50%);
			opacity: 1;
		}
		100% {
			left: 0;
			box-shadow: -100px 0 0 var(--circlesColor);
		}
	}
	@keyframes circlesRight {
		0% {
			right: 0;
			box-shadow: 100px 0 0 var(--circlesColor);
		}
		10% {
			right: 50%;
			box-shadow: -30px 0 0 var(--circlesColor);
			transform: translateX(50%) translateY(-50%);
			opacity: 1;
		}
		90% {
			right: 50%;
			box-shadow: -30px 0 0 var(--circlesColor);
			transform: translateX(50%) translateY(-50%);
			opacity: 1;
		}
		100% {
			right: 0;
			box-shadow: 100px 0 0 var(--circlesColor);
		}
	}
	@keyframes fill {
		0% {
			transform: scale(0);
		}
		15% {
			transform: scale(0);
		}
		30% {
			transform: scale(1);
		}
		70% {
			transform: scale(1);
		}
		85% {
			transform: scale(0);
		}
		100% {
			transform: scale(0);
		}
	}
	@keyframes fadeIn{
		0% {
			opacity: 0;
		}
		15% {
			opacity: 0;
		}
		30% {
			opacity: 1;
		}
		65% {
			opacity: 1;
		}
		80% {
			opacity: 0;
		}
		100% {
			opacity: 0;
		}
	}
	@keyframes fadeOut{
		0% {
			opacity: 1;
		}
		15% {
			opacity: 1;
		}
		25% {
			opacity: 0;
		}
		70% {
			opacity: 0;
		}
		80% {
			opacity: 1;
		}
		100% {
			opacity: 1;
		}
	}
	@keyframes fadeInHover{
		0% {
			opacity: 0;
		}
		15% {
			opacity: 0;
		}
		30% {
			opacity: 1;
		}
		65% {
			opacity: 1;
		}
		80% {
			opacity: 1;
		}
		100% {
			opacity: 1;
		}
	}
	@keyframes fadeOutHover{
		0% {
			opacity: 1;
		}
		15% {
			opacity: 1;
		}
		25% {
			opacity: 0;
		}
		70% {
			opacity: 0;
		}
		80% {
			opacity: 0;
		}
		100% {
			opacity: 0;
		}
	}
	
	.background {
		width: var(--areaWidth);
		height: var(--areaHeight);
		padding-top: 10px;
		padding-bottom: 10px;
		background-color: var(--areaBackgroundColor);
		position: relative;
		z-index: 1;
		display: flex;
		justify-content: center;
		align-items: center;
	}
	a.click {
		display: inline-block;
		text-decoration: none;
		color: var(--color);
		width: var(--btnWidth);
		height: var(--btnHeight);
		font-size: var(--fontSize);
		position: relative;
		line-height: 80px;
		text-align: center;
		display: flex;
		justify-content: center;
		align-items: center;

		cursor: pointer;
		&:focus {
			animation: changeFontColor var(--animationDuration) linear alternate;
		}
		&:active {
			animation: none;
		}

		&:before,
		&:after {
			content: '';
			width: var(--circlesSize);
			height: var(--circlesSize);
			position: absolute;
			top: 50%;
			transform: translateY(-50%);
			background-color: var(--circlesColor);
			border-radius: 50%;
			z-index: -2;
			opacity: 0;
		}

		&:after {
			right: 0;
			box-shadow: 100px 0 0 var(--circlesColor);
		}
		&:before {
			left: 0;
			box-shadow: -100px 0 0 var(--circlesColor);
		}
		&:focus:before {
			animation: circlesLeft var(--animationDuration) linear alternate;
		}
		&:active:before {
			animation: none;
		}
		&:focus:after {
			animation: circlesRight var(--animationDuration) linear alternate;
		}
		&:active:after {
			animation: none;
		}
		span.btn-background {
			position: absolute;
			top: 0;
			left: 0;
			width: 100%;
			height: 100%;
			background-color: var(--btnBackgroundColor);
			z-index: -1;
			border-radius: 8px;
			transform: scale(0);
		}

		&:focus span.btn-background {
			animation: fill var(--animationDuration) linear alternate;
		}
		&:active span.btn-background {
			animation: none;
		}
		span.start-text{
			position: absolute;
			opacity: 1;	
		}
		&:focus span.start-text{
			animation: fadeOut var(--animationDuration) linear normal ; 
			animation-fill-mode: both;
		}
		&:active span.start-text{
			animation: none;
		}
		span.end-text{
			opacity: 0;
			position: absolute;
		}
		&:focus span.end-text{
			animation: fadeIn var(--animationDuration) linear normal ;  
			animation-fill-mode: both;
		}
		&:active span.end-text{
			animation: none;
		}
	}
	a.hover {
		display: inline-block;
		text-decoration: none;
		color: var(--color);
		width: var(--btnWidth);
		height: var(--btnHeight);
		font-size: var(--fontSize);
		position: relative;
		line-height: 80px;
		text-align: center;
		display: flex;
		justify-content: center;
       	align-items: center;
		transition: all var(--animationDuration);
		cursor: pointer;
		&:hover{
			color: var(--fontAnimationColor);
			transition-delay: var(--animationDelay);
			
		}

		&:before,
		&:after {
			content: "";
			width: var(--circlesSize);
			height: var(--circlesSize);
			position: absolute;
			top: 50%;
			transform: translateY(-50%);
			background-color: var(--circlesColor);
			transition: all var(--animationDuration);
			border-radius: 50%;
			z-index: -2;
			opacity: 0;
		}
		&:after {
			right: 0;
			box-shadow: 100px 0 0 var(--circlesColor);
		}
		&:before {
			left: 0;
			box-shadow: -100px 0 0 var(--circlesColor);
		}
		&:hover:before {
			left: 50%;
			box-shadow: 30px 0 0 var(--circlesColor);
			transform: translateX(-50%) translateY(-50%);
			opacity: 1;
		}
		&:hover:after {
			right: 50%;
			box-shadow: -30px 0 0 var(--circlesColor);
			transform: translateX(50%) translateY(-50%);
			opacity: 1;
			
		}
		span.btn-background{
			position: absolute;
			top: 0;
			left: 0;
			width: 100%;
			height: 100%;
			background-color: var(--btnBackgroundColor);
			transform: scale(0);
			transition: all var(--animationDuration);
			z-index: -1;
			border-radius: 8px;
		}
		&:hover span.btn-background{
				transform: scale(1);
				transition-delay: var(--animationDelay);
		}
		span.start-text{
			position: absolute;
			opacity: 1;	
		}
		&:hover span.start-text{
			animation: fadeOutHover var(--animationDuration) linear  var(--animationDelay) normal; 
			animation-fill-mode: both;
		}

		span.end-text{
			opacity: 0;
			position: absolute;
		}
		&:hover span.end-text{
			animation: fadeInHover var(--animationDuration) linear  var(--animationDelay) normal;  
			animation-fill-mode: both;
		}
	}

</style>
