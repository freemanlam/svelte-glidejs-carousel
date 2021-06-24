<script>
  import Carousel from './carousel.svelte';
  import CarouselSlide from './carousel-slide.svelte';
</script>

<Carousel>
  <CarouselSlide>
    <div style="background: red">1</div>
  </CarouselSlide>
  <CarouselSlide>
    <div style="background: green">2</div>
  </CarouselSlide>
  <CarouselSlide>
    <div style="background: blue">3</div>
  </CarouselSlide>
</Carousel>

<style>
  div {
    color: #fff;
    display: flex;
    font-size: 3em;
    min-height: 100vh;
    align-items: center;
    justify-content: center;
  }
</style>
