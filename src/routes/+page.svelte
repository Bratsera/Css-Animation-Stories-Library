<script>
    import RotateIn from "$lib/Buttons/RotateIn.svelte";
    import SlideFill from "$lib/Buttons/SlideFill.svelte";
    import SlideAll from "$lib/Buttons/SlideAll.svelte";
    import ButtonShine from "$lib/Buttons/ButtonShine.svelte";
</script>

    <RotateIn  animationBackgroundColor="#fff200" animationDuration="1s">Hello</RotateIn>
    <SlideFill>Change Color</SlideFill>
    <SlideAll>Change Color</SlideAll>
    <ButtonShine  animationBackgroundColor="red"  ></ButtonShine>

<style lang="less">
    :root{
        box-sizing: border-box;
       
    }
</style>
