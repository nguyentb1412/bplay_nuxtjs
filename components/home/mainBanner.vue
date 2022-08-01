<template>
  <section>
    <div class="banner">
      <img src="/assets/images/desktop/banner/title.png" class="img-title pc-title" alt="">
      <img src="/assets/images/mobile/banner/title.png" class="img-title mb-title" alt="">
      <img src="/assets/images/desktop/banner/banner.png" alt="banner" class="img-banner pc-banner">
      <img src="/assets/images/mobile/banner/banner.png" alt="banner" class="img-banner mb-banner">
      <div class="scroll mb-scroll">
        <span>Scroll</span>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  components: {

  },
  mounted() {
      $(".mb-scroll").click(function() {
          $('html, body').animate({
              scrollTop: $(".about-us-container").offset().top
          }, 2000);
      });
  }
}
</script>
