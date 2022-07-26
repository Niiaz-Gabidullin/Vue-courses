<template>
  <div class="container">
    <div class="card">
      <h1 class="text">Actual news {{ now }}</h1>
      <span>Open: {{ openRate }} | read: {{ readRate }}</span>
      <hr width="90%" size="1 px" color="#dddddd" />
    </div>
    <app-news v-for="item in news" :title="item.title" :key="item.id" :id="item.id" :is-open="item.isOpen"
      :was-read="item.wasRead" @open-news="openNews" @read-news="readNews"></app-news>

  </div>
</template>

<script>

import AppNews from './AppNews.vue'

export default {
  name: 'App',
  data() {
    return {
      now: new Date().toLocaleDateString(),
      openRate: 0,
      readRate: 0,
      news: [
        {
          title: "I have been programming for 2 years",
          id: 1,
          isOpen: false,
          wasRead: false,
        },
        {
          title: "he have been programming for 2 years",
          id: 2,
          isOpen: false,
          wasRead: false,
        },
        {
          title: "she have been programming for 2 years",
          id: 3,
          isOpen: false,
          wasRead: false,
        }

      ]
    }
  },

  methods: {
    openNews() {
      this.openRate++

    },
    readNews() {
      this.readRate++
    }
  },
  components: {
    "app-news": AppNews,
  }
}
</script>

<style>
</style>
