<template>
<v-main>
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
        <v-btn  icon plain @click="selectUnit(index)" to="/unit"
        :class="hover ? 'd-block mx-auto my-2' : 'd-block mx-auto my-1'" >
        <v-icon 
        :size="hover ? 30 : 25">
        
        mdi-numeric-{{index+1}}-box
        </v-icon>
      </v-btn>
      </v-avatar>
    </v-hover>   
    </v-navigation-drawer>
  
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
    <v-container>
    <v-row no-gutters>
    <v-col v-for="(unit, index) in this.sectionInfo.units" :key="index" cols="12">
        <v-card class="pa-2" tile>
            <v-card-title>
                {{unit.title}}
            </v-card-title>
            <v-card-subtitle>
                {{unit.description}}
            </v-card-subtitle>
        </v-card>
    </v-col>
    </v-row>
    </v-container>
</v-app>    
</v-main>
</template>

<script>
    import section from "../static/json/techthreatre.json";
    import VueCookies from 'vue-cookies';
  export default {
    name:"TechTheatre",
    icons: {
    iconfont: 'mdi', 
  },
  data: () => ({
      sectionInfo: section,
  }),
  layout: "section",

  methods: {
    selectUnit(n){
        VueCookies.set("unit", n,'1m')
        },
  }
  }
</script>

