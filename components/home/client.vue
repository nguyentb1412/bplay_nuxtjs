<template>
  <div class="clients" id="clients-section">
    <h2 class="title text-uppercase wow fadeInUp" >
      <span class="title__sub">BPLAY GAME</span>
      OUR CLIENTS
    </h2>
    <div class="client-images-container wow fadeInUp" >
      <ul>
        <li v-for="(item, index) in listClient" :key="index">
          <a href="#.">
            <img :class="item.class" :src="item.url" alt />
          </a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      listClient: [
        {
          class: 'client-image',
          url: '/assets/images/desktop/client/9.png',
        },
        {
          class: 'client-image',
          url: '/assets/images/desktop/client/12.png',
        },
        {
          class: 'client-image',
          url: '/assets/images/desktop/client/16.png',
        },
        {
          class: 'client-image',
          url: '/assets/images/desktop/client/bet365.png',
        },
        {
          class: 'client-image',
          url: '/assets/images/desktop/client/betfair.png',
        },
        {
          class: 'client-image',
          url: '/assets/images/desktop/client/betway.png',
        },
        {
          class: 'client-image',
          url: '/assets/images/desktop/client/bwin.png',
        },
        {
          class: 'client-image',
          url: '/assets/images/desktop/client/williamhill.png',
        },
        {
          class: 'client-image',
          url: '/assets/images/desktop/client/1.png',
        },
        {
          class: 'client-image',
          url: '/assets/images/desktop/client/2.png',
        },
        {
          class: 'client-image',
          url: '/assets/images/desktop/client/clients11.png',
        },
        {
          class: 'client-image',
          url: '/assets/images/desktop/client/clients12.png',
        },
      ],
    }
  },
}
</script>
