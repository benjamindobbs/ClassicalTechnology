

<template>
<v-main>
    <v-app>
        <v-card>
            <v-card-title>
               unit: {{unit}}
            </v-card-title>
        </v-card>
    </v-app>
</v-main>
    
</template>
<script>
import VueCookies from 'vue-cookies';
export default {
        data: () => ({
            unit:'test'
        }),
        methods: {
            getUnit() {
               unit = VueCookies.get('unit');
            },
        },
        mounted () {
            this.getUnit();
        }
    }
</script>
