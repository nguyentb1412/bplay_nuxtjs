<template>
  <section class="igaming-container">
    <div class="igaming-container__box">
      <p class="igaming-container__box__number" :data-year="year">
        {{ this.year }}
      </p>
      <p class="igaming-container__box__year wow fadeInLeft" >
        YEARS
      </p>
      <p class="igaming-container__box__text wow fadeInUp" >of experience<br />in the <span>iGaming</span></p>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      year: 15,
    }
  },
  components: {},
  mounted() {},
}
</script>
