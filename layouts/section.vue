<template>
  <v-app light id="inspire">
      <v-navigation-drawer
        absolute
        permanent
        right
        floating
        mini-variant
      >
        <v-hover 
        v-slot="{ hover }">

      <v-avatar
        left
        :size="hover ? 50 : 40"
        :color="`grey ${hover ? 'darken' : 'lighten'}-1`"
        class="d-block text-center mx-auto mb-6 mt-10"
      >
        <v-btn to="/" icon plain 
        :class="hover ? 'd-block mx-auto my-3' : 'd-block mx-auto my-2'" >
        <v-icon 
        :size="hover ? 30 : 25">
        mdi-home</v-icon>
      </v-btn>
      </v-avatar>

      </v-hover>
      <v-hover 
        v-slot="{ hover }">
      <v-avatar
        left
        :size="hover ? 50 : 40"
        :color="`grey ${hover ? 'darken' : 'lighten'}-1`"
        class="d-block text-center mx-auto mb-5"
      >
  
        <v-btn @click="goBack" icon plain 
        :class="hover ? 'd-block mx-auto my-2' : 'd-block mx-auto my-1'" >
        <v-icon 
        :size="hover ? 30 : 25">
        mdi-arrow-left</v-icon>
      </v-btn>
      </v-avatar>
    </v-hover>   
      </v-navigation-drawer>
    <nuxt/>
    </v-app>
    
    </template>
<script>
    export default {
        methods: {
            goBack() {
                this.$router.go(-1)
            },
        },
    }
</script>