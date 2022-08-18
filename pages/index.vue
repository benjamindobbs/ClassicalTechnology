<template>
  <v-row justify="center">
    <v-col cols="12" sm="8" md="6">
      <v-card class="logo py-4 d-flex justify-center">
        <v-img src="TechnologyLogo.svg" contain>
        </v-img>
      </v-card>
      <v-card>
        <v-card-title class="headline">
          Welcome to Classical Technology
        </v-card-title>
        <v-card-text>
          <p>Navigate to your class to find information regarding the course.</p>
          <p>
           Or look through our program of studies to get an overview of our program.
          </p>
          <p>
            If you have questions, feel free to email either of our Technology Educators: 
            <br>
            <v-card flat>
              <v-card-text class="d-flex justify-space-around">
                <a
                  href="mailto:lestl001@hartfordschools.org"
                  target="_blank"
                >
                  Lou Lestini 
                </a>
                <a
                  href="mailto:dobbb001@hartfordschools.org"
                  target="_blank"
                >
                  Ben Dobbs
                </a>
              </v-card-text>
            </v-card>
          </p>
        </v-card-text>
      </v-card>      
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: "IndexPage",
};
</script>
