<script>
    import RotateIn from "$lib/Buttons/RotateIn.svelte";
    import SlideFill from "$lib/Buttons/SlideFill.svelte";
    import SlideAll from "$lib/Buttons/SlideAll.svelte";
    import ButtonShine from "$lib/Buttons/ButtonShine.svelte";
    import LetterStretch from "$lib/Buttons/LetterStretch.svelte";
    import Swaping from "$lib/Buttons/Swaping.svelte";
    import LetterScale from '$lib/Buttons/LetterScale.svelte';
    import SlideRoundedFill from '$lib/Buttons/SlideRoundedFill.svelte';
</script>
    <LetterScale></LetterScale>
    <RotateIn  animationBackgroundColor="#fff200" animationDuration="1s">Hello</RotateIn>
    <SlideFill>Change Color</SlideFill>
    <SlideAll>Change Color</SlideAll>
    <ButtonShine  animationBackgroundColor="red"  ></ButtonShine>
    <LetterStretch>Let it grow</LetterStretch>
    <Swaping></Swaping>
    <SlideRoundedFill></SlideRoundedFill>
<style lang="less">
    :root{
        box-sizing: border-box;
       
    }
</style>
