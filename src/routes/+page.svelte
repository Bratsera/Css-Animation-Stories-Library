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
    import Wide3CirclesFusion from "$lib/Buttons/Wide3CirclesFusion.svelte";
</script>
    <LetterScale></LetterScale>
    <hr>
    <RotateIn  animationBackgroundColor="#fff200" animationDuration="1s">Hello</RotateIn>
    <hr>
    <SlideFill>Change Color</SlideFill>
    <hr>
    <SlideAll>Change Color</SlideAll>
    <hr>
    <ButtonShine  animationBackgroundColor="red"  ></ButtonShine>
    <hr>
    <LetterStretch>Let it grow</LetterStretch>
    <hr>
    <SwapLeft2Right></SwapLeft2Right>
    <hr>
    <SlideRoundedFill></SlideRoundedFill>
    <hr>
    <SwapDiagonal></SwapDiagonal>
    <hr>
    <Wide3CirclesFusion></Wide3CirclesFusion>
<style lang="less">
 
    :root{
        box-sizing: border-box;
       display: flex;
       justify-content: center;
       align-items: center;
       width: 100%;
       height: 100%;
    }
</style>
