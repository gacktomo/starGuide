<template>
  <v-ons-page>
    <v-ons-toolbar class="home-toolbar">
      <div class="left">
        <v-ons-toolbar-button @click="$store.commit('splitter/toggle')">
          <v-ons-icon icon="fa-bars"></v-ons-icon>
        </v-ons-toolbar-button>
      </div>
      <div class="center">{{ msg }}</div>
    </v-ons-toolbar>

    <vue-event-calendar :events="demoEvents"></vue-event-calendar>

  </v-ons-page>
</template>

<script>
export default {
  name: 'home',
  compornents: {
  },
  data () {
    return {
      demoEvents: [
        {
          date: '2016/11/12', // Required
          title: 'Foo' // Required
        }, 
        {
          date: '2016/12/15',
          title: 'Bar',
          desc: 'description',
          customClass: 'disabled highlight' // Custom classes to an calendar cell
        }
      ],
      msg: 'Welcome',
      essentialLinks: [
        {
          label: 'Core Docs',
          link: 'https://vuejs.org',
          icon: 'fa-book'
        },
      ]
    }
  },
  methods: {
    goTo (url) {
      const newWindow = window.open(url, '_blank')
      newWindow.opener = null
      newWindow.location = url
    }
  }
}
</script>

<style scoped>
</style>
