<template lang="pug">
  v-toolbar(
    :class="[$store.state.currentColor]"
    fixed
    dark
    app
  )#main-toolbar
    v-toolbar-side-icon(@click.stop="toggleSidebar")

    transition(name="slide" mode="out-in")
      v-toolbar-title(
        v-html="$store.state.h1"
        style="position: relative"
        v-bind:key="$store.state.h1"
        class="d-flex"
      )
    v-spacer
    v-tooltip(bottom)
      v-btn(
        icon
        href="https://www.twitch.tv/johnleider"
        target="_blank"
        rel="noopener"
        large
        slot="activator"
      ).mr-3
        v-icon fa-fw fa-twitch
      span Twitch stream
</template>

<script>
  export default {
    name: 'toolbar',

    methods: {
      toggleSidebar () {
        this.$store.commit('vuetify/SIDEBAR', !this.$store.state.sidebar)
      }
    }
  }
</script>
