<template>
  <main>
    <Menu />
    <Nuxt />
    <Footer />
  </main>
</template>

<script>
import Footer from '../components/footer.vue'
import Menu from '../components/menu.vue'
export default {
  components: {
    Footer,
    Menu,
  },
  head() {
    return {
      link: [
        {
          type: 'text/css',
          rel: 'stylesheet',
          href: `/assets/lib/slick.css`,
        },
         {
          type: 'text/css',
          rel: 'stylesheet',
          href: `/assets/lib/animate.css`,
        },
      ],
      __dangerouslyDisableSanitizers: ['script'],
      script: [
        {
          src: `/assets/lib/jquery.min.js`,
          defer: true,
          body: true,
        },
        // {
        //   src: `/assets/lib/slick.min.js`,
        //   defer: true,
        //   body: true,
        // },
        {
          src: `/assets/lib/wow.min.js`,
          defer: true,
          body: true,
        },
      ],
      meta: [
        {
          name: 'viewport',
          content: 'width=device-width, initial-scale=1.0, maximum-scale=1.0',
        },
      ],
      bodyAttrs: {
        class: '',
        ref: 'body',
      },
    }
  },
  mounted() {
  },
}
</script>
