<template>
  <v-toolbar dark color="primary">
    <v-toolbar-side-icon></v-toolbar-side-icon>

    <v-toolbar-title class="white--text">
        标题
    </v-toolbar-title>

    <v-spacer></v-spacer>

    <v-btn icon>
      <v-icon>search</v-icon>
    </v-btn>

    <v-btn icon>
      <v-icon>apps</v-icon>
    </v-btn>

    <v-btn icon>
      <v-icon>refresh</v-icon>
    </v-btn>

    <v-btn icon>
      <v-icon>more_vert</v-icon>
    </v-btn>
  </v-toolbar>
</template>

<script>
  export default {
    data () {
      return {
        name:"我的首页"
      }
    }
  }
</script>

<style>

</style>
