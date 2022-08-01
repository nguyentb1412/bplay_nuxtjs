<template>
  <section class="product" id="products-section">
    <div class="product-container">
      <div class="row">
        <div class="col-12 col-md-4 wow fadeInLeft">
          <h2 class="title">
            <span class="title__sub">BPLAY GAME</span>
            OUR PRODUCTS
          </h2>
        </div>
        <div class="col-12 col-md-8 col-lg-7 wow fadeInRight">
          <p class="product-container__description">
            BPlay’s high quality iGaming Platform offers a complete solution for your casino. Get the full White Label turnkey solution or the Seamless API with our comprehensive selection of games.
            Through our global network of premium partners such as Vivo Gaming, SBTech and HoGaming you will have access to the best Live Casino, Sportsbook, Slots, Table Games, Number Games and
            Fishing Games on the market.
          </p>
        </div>
      </div>
      <div class="row product-container__items">
        <div class="col-12 col-sm-4" v-for="(item, index) in slider" :key="index">
          <figure class="product-container__items__box">
            <a href="#." class="product-container__items__link">
              <img class="product-container__items__box__img wow fadeInUp" data-wow-duration="1s" :src="item.url" :alt="item.name" />
            </a>
            <figcaption>
              <h3 class="product-container__items__box__title">
                <a class="product-container__items__box__title__link" href="#" tabindex="0">{{ item.name }}</a>
              </h3>
              <p class="product-container__items__box__description">{{ item.title }}</p>
            </figcaption>
          </figure>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import slick from '../../static/assets/lib/slick.min.js'

export default {
  data() {
    return {
      slickOption: {
        centerMode: false,
        slidesToShow: 9,
        arrows: false,
        autoplay: true,
        responsive: [
          {
            breakpoint: 768,
            settings: {
              dots: true,
              centerMode: true,
              slidesToShow: 2,
            },
          },
          {
            breakpoint: 600,
            settings: {
              dots: true,
              slidesToShow: 2,
            },
          },
          {
            breakpoint: 420,
            settings: {
              dots: true,
              slidesToShow: 1,
              centerMode: true,
            },
          },
        ],
      },
      slider: [
        {
          url: '/assets/images/desktop/game/live-casino.png',
          name: 'Live Casino',
          title: 'Vivo LiveCasino, HoGaming Live Casino, BPlay LiveCasino',
        },
        {
          url: '/assets/images/desktop/game/fishing-game.png',
          name: 'Fishing Game',
          title: 'BPlay Fishing 2D, BPlay Fishing 3D',
        },
        {
          url: '/assets/images/desktop/game/sport-book.png',
          name: 'Sport Book',
          title: 'BTI Sportsbook, BPlay Sportsbook',
        },
        {
          url: '/assets/images/desktop/game/numbergame.png',
          name: 'Quick Number',
          title: 'Keno, Number Games, Lottery',
        },
        {
          url: '/assets/images/desktop/game/white-label.png',
          name: 'White Label',
          title: 'Bplay White Label',
        },
        {
          url: '/assets/images/desktop/game/jackpot-slots.png',
          name: 'Slots',
          title: 'BPlay Slots, Jackpot Slots',
        },
        {
          url: '/assets/images/desktop/game/full-package.png',
          name: 'Seamless API',
          title: 'Seamless API',
        },
        {
          url: '/assets/images/desktop/game/tablegame.png',
          name: 'Full Package',
          title: 'VFull Package',
        },
        {
          url: '/assets/images/desktop/game/seamless.png',
          name: 'Table Game',
          title: 'Table Game',
        },
      ],
    }
  },
  methods: {
    initSlider() {
      $('.product-container__items').slick(this.slickOption)
    },
  },

  mounted() {
    this.initSlider()
  },
}
</script>

