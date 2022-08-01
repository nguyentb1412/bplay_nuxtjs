<template>
  <header>
    <nav class="menu navbar navbar-expand-lg navbar-dark">
      <a class="navbar-brand" href="#">
        <img src="/assets/images/desktop/menu-logo/Logo.svg" alt="Bplay"/>
      </a>
      <button class="navbar-toggler btn-open" type="button" @click.prevent="showMenu">
        <span class="navbar-toggler-icon mb-ic-open"></span>
      </button>
      <button class="navbar-toggler btn-close hide" type="button" @click.prevent="hideMenu">
        <span class="navbar-toggler-icon mb-ic-close"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNavDropdown">
        <ul class="navbar-nav">
          <li class="nav-item active" id="about-us">
            <a class="nav-link" href="#about-us-section">
              ABOUT US
              <span class="sr-only">(current)</span>
            </a>
          </li>
          <li class="nav-item" id="product">
            <a class="nav-link" href="#products-section">PRODUCTS</a>
          </li>
          <li class="nav-item" id="partners">
            <a class="nav-link" href="#partners-section">PARTNERS</a>
          </li>
          <li class="nav-item" id="clients">
            <a class="nav-link" href="#clients-section">OUR CLIENTS</a>
          </li>
          <li class="nav-item" id="contact-us">
            <a class="nav-link" href="#contact-us-section">CONTACT US</a>
          </li>
        </ul>
      </div>
      <div class="select">
        <ul>
          <li class="option">
            <img src="/assets/images/desktop/menu-logo/en.png" alt="EN"/>
            <span>ENG</span>
          </li>
          <li class="option">
            <img src="/assets/images/desktop/menu-logo/vi.png" alt="VI"/>
            <span>VI</span>
          </li>
        </ul>
      </div>
    </nav>
  </header>
</template>
<script>
export default {
  components: {},
  methods: {
    showMenu() {
      $('.btn-open').addClass('hide');
      $('.btn-close').removeClass('hide');
      $('#navbarNavDropdown').addClass('show');
      $('header').addClass('active');
      $('.select').addClass('select-left');
      $('.navbar-brand').addClass('invisible');
      $('body').addClass('overflow-hidden');
    },
    hideMenu() {
      $('.btn-open').removeClass('hide');
      $('.btn-close').addClass('hide');
      $('#navbarNavDropdown').removeClass('show');
      $('header').removeClass('active');
      $('.select').removeClass('select-left');
      $('.navbar-brand').removeClass('invisible');
      $('body').removeClass('overflow-hidden');
    },
  },
  mounted() {
    $('.select ul li.option').click(function () {
      $(this).siblings().toggle();
      $(this).parent().prepend(this);
    });

    $('#navbarNavDropdown > ul > li.nav-item').click(function () {
      $('.nav-item').removeClass('active');
      $(this).addClass('active');
      $('.btn-open').removeClass('hide');
      $('.btn-close').addClass('hide');
      $('#navbarNavDropdown').removeClass('show');
      $('header').removeClass('active');
      $('.select').removeClass('select-left');
      $('.navbar-brand').removeClass('invisible');
      $('body').removeClass('overflow-hidden');
    });
    var isWow = false,
      flag = true
    $(window).scroll(function () {
      if (elementInView($('.about-us-container'))) {
        if (!isWow) {
          activeWow()
        }
        $('.nav-item').removeClass('active')
        $('#about-us').addClass('active')
      } else if (elementInView($('.product'))) {
        if (!isWow) {
          activeWow()
        }
        $('.nav-item').removeClass('active')
        $('#product').addClass('active')
      } else if (elementInView($('.partners'))) {
        if (!isWow) {
          activeWow()
        }
        $('.nav-item').removeClass('active')
        $('#partners').addClass('active')
      } else if (elementInView($('.clients'))) {
        if (!isWow) {
          activeWow()
        }
        $('.nav-item').removeClass('active')
        $('#clients').addClass('active')
      } else if (elementInView($('.contact-us'))) {
        if (!isWow) {
          activeWow()
        }
        $('.nav-item').removeClass('active')
        $('#contact-us').addClass('active')
      }

      if (elementInView($('.about-us-container'), true)) {
        if (!isWow) {
          activeWow()
        }
        if (flag) counterNumber()
      }
    });

    function activeWow() {
      const WOW = require('wowjs')
      window.wow = new WOW.WOW({
        live: false,
      });
      window.wow.init();
      isWow = true
    }

    function elementInView(elem, isCountingYears = false) {
      const elemTop = $(elem).offset().top
      const elemHeight = $(elem).height()
      const haftWindowHeight = $(window).height() / 2
      if (isCountingYears) {
        return $(window).scrollTop() < elemTop + elemHeight && $(window).scrollTop() > elemTop
      }
      return $(window).scrollTop() < elemTop + elemHeight && elemTop + elemHeight - $(window).scrollTop() > haftWindowHeight
    }

    function counterNumber() {
      Number.prototype.format = function (n) {
        var r = new RegExp('\\d(?=(\\d{3})+' + (n > 0 ? '\\.' : '$') + ')', 'g');
        return this.toFixed(Math.max(0, Math.floor(n))).replace(r, '$&,');
      };
      $('.igaming-container__box__number').each(function (e) {
        $(this)
          .prop('counter', 1)
          .animate(
            {
              counter: $(this).data('year'),
            },
            {
              duration: 3000,
              step: function (step) {
                $(this).text('' + step.format())
              },
            }
          )
      });
      flag = false
    }
    $(window).on('scroll', function () {
      let scroll = $(window).scrollTop();
      if (scroll > 0) {
          $('header').addClass('sticky-header');
          if (screen.width > 991) {
              $('.select').addClass('top-pc');
          }
      } else {
          $('header').removeClass('sticky-header');
          $('.select').removeClass('top-pc');
      }
    })
  },
}
</script>
