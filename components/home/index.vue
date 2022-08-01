<template>
  <div>
     <main-banner />
     <about-us />
     <i-gaming />
     <product />
     <partner />
     <client />
    <div class="pagetop">
      <a href="#">Top</a>
    </div>
  </div>
</template>

<script>
import mainBanner from './mainBanner'
import AboutUs from './aboutUs'
import Product from './product'
import Partner from './partner'
import Client from './client'
import IGaming from './iGaming'

export default {
  components: {
    IGaming,
    Client,
    Partner,
    Product,
    AboutUs,
    mainBanner
  },
  mounted() {
      $(window).scroll(function() {
          if ($(this).scrollTop() > 100) {
              $('.pagetop').addClass('active');
          } else {
              $('.pagetop').removeClass('active');
          }
      });

      $(".pagetop a").click(function() {
          $("html, body").animate({ scrollTop: 0 }, "slow");
          return false;
      });
  }
}
</script>
