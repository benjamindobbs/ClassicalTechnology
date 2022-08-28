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
        <unitPage v-if="unitSelected"
        :unit="unit"
        :sectionInfo="sectionInfo"
        />
        <v-container v-else>
            <v-row
            justify="center"
            >
                <v-col
                cols="12"
                class="d-flex flex-wrap justify-space-around"
                >
                    <v-card
                    v-for="(unit,index) in this.sectionInfo.units"
                    :key="index"
                    outlined
                    rounded
                    class="ma-5">
                        <v-card-title>
                            Unit: {{index+1}} {{unit.title}}
                        </v-card-title>
                        <v-card-subtitle>
                            {{unit.description}}
                        </v-card-subtitle>
                    </v-card>
                </v-col>
            </v-row>
        </v-container>   
    </v-main>
    </v-app>
  </template>
  <script>
    import unitPage from '@/components/unit.vue'
    export default {
        name: 'classInfo',
        props: {
            sectionInfo: JSON,

        },
        data: () => ({
            unit:0,
            unitSelected:false,
        }),
        methods: {
        selectUnit(n){
            this.unit = n;
            this.unitSelected=true;
            },
        },
        components: {
        unitPage,
        },
    }   
</script>