<template>
  <v-app light id="inspire">
    <nuxt/>
    <v-navigation-drawer
      app
      class="pt-4"
      color="grey lighten-3"
      mini-variant
    >
    <v-hover 
        v-slot="{ hover }"
        v-for="(section, index) in this.sectionInfo.units"
        :key="index"> 
      
      <v-avatar
        left
        :size="hover ? 50 : 40"
        :color="`grey ${hover ? 'darken' : 'lighten'}-1`"
        class="d-block text-center mx-auto mb-9"
      > 
        <v-btn  icon plain @click="selectUnit(index)"
        :class="hover ? 'd-block mx-auto my-2' : 'd-block mx-auto my-1'" >
        <v-icon 
        :size="hover ? 30 : 25">
        
        mdi-numeric-{{index+1}}-box
        </v-icon>
      </v-btn>
      </v-avatar>
    </v-hover>   
  </v-navigation-drawer>  
  
  <v-main>    
  <v-card>
      <v-card-title>
          Welcome to {{ this.sectionInfo.sectioninfo[0].title }}
      </v-card-title>
      <v-card-subtitle>
          {{this.sectionInfo.sectioninfo[0].description}}
          <br>
          {{this.sectionInfo.sectioninfo[0].teacher}}
      </v-card-subtitle>
    </v-card>
    <unitPage
      :unit="unit"
    />   
 
  </v-main>
</v-app>
</template>

<script>
    import section from "../static/json/techthreatre.json";
    import unitPage from '@/components/unit.vue'
  export default {
    name:"TechTheatre",
    icons: {
    iconfont: 'mdi', 
  },
  data: () => ({
      sectionInfo: section,
      unit:0
  }),
  layout: "section",

  methods: {
    selectUnit(n){
        this.unit = n;
        },
  },
  components: {
    unitPage,
  }
  }
</script>

