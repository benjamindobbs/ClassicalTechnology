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
        v-for="(section, index) in navbar"
        :key="index"> 
      
      <v-avatar
        left
        :size="hover ? 50 : 40"
        :color="`grey ${hover ? 'darken' : 'lighten'}-1`"
        class="d-block text-center mx-auto mb-9"
      > 
          <v-btn :to="section.path" icon plain 
          :class="hover ? 'd-block mx-auto my-3' : 'd-block mx-auto my-2'" >
            <v-icon 
            :size="hover ? 30 : 25">
            {{section.icon}}
            </v-icon>
          </v-btn>
        
      </v-avatar>
      
    </v-hover>   
    </v-navigation-drawer>
  </v-app>
</template>

<script>
  export default {
    icons: {
    iconfont: 'mdi', 
  },
    data: () => ({
      navbar: [
        {name:"home",path:"/",icon:"mdi-home"},
        {name:"ECS",path:"/ECS",icon:"mdi-laptop"},
        {name:"Robotics",path:"/robotics",icon:"mdi-robot-industrial"},
        {name:"3D Modeling",path:"/3D",icon:"mdi-blender-software"},
        {name:"Technical Theatre",path:"TechTheatre",icon:"mdi-curtains"},
        {name:"Graphics",path:"graphics",icon:"mdi-brush"},
        {name:"6th Grade Technology",path:"6thGrade",icon:"mdi-numeric-6-box"},
        {name:"7th Grade Technology", path:"7thGrade",icon:"mdi-numeric-7-box"},
        {name:"8th Grade Technology",path:"8thGrade",icon:"mdi-numeric-8-box"},

      ],
    })

  }
</script>
