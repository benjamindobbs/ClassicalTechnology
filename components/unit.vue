<template>
<v-main>
<v-container>
    <v-row no-gutters>
    <v-col>
      <v-card-title>
        {{this.sectionInfo.units[unit].title}}
      </v-card-title>
      <v-card-subtitle>
        {{this.sectionInfo.units[unit].description}}
      </v-card-subtitle>
    </v-col>
    <v-col v-for="(assignment, index) in this.sectionInfo.units[unit].assignment" :key="index" cols="12">
        <v-card class="pa-2" tile>
            <v-card-title>
                {{assignment.title}}
            </v-card-title>
            <v-card-subtitle>
                {{assignment.resources}}
            </v-card-subtitle>
        </v-card>
    </v-col>
    </v-row>
    </v-container>
    </v-main>
</template>
<script>

    export default {
        name: 'unit',
        props: {
            unit: Number,
            sectionInfo: JSON,

        },
        data: () => ({
        })
    }
</script>
