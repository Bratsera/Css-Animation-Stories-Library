<script>
    import RotateIn from "$lib/Buttons/RotateIn.svelte";
    import SlideFill from "$lib/Buttons/SlideFill.svelte";
    import SlideAll from "$lib/Buttons/SlideAll.svelte";
    import ButtonShine from "$lib/Buttons/ButtonShine.svelte";
    import LetterStretch from "$lib/Buttons/LetterStretch.svelte";
    import SwapLeft2Right from "$lib/Buttons/SwapLeft2Right.svelte";
    import LetterScale from '$lib/Buttons/LetterScale.svelte';
    import SlideRoundedFill from '$lib/Buttons/SlideRoundedFill.svelte';
    import SwapDiagonal from "$lib/Buttons/SwapDiagonal.svelte";
</script>
    <LetterScale></LetterScale>
    <RotateIn  animationBackgroundColor="#fff200" animationDuration="1s">Hello</RotateIn>
    <SlideFill>Change Color</SlideFill>
    <SlideAll>Change Color</SlideAll>
    <ButtonShine  animationBackgroundColor="red"  ></ButtonShine>
    <LetterStretch>Let it grow</LetterStretch>
    <SwapLeft2Right></SwapLeft2Right>
    <SlideRoundedFill></SlideRoundedFill>
    <SwapDiagonal></SwapDiagonal>
<style lang="less">
    :root{
        box-sizing: border-box;
       
    }
</style>
