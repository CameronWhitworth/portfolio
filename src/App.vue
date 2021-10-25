<template>
  <div id="app">
    <v-app>
      <!-- <v-app-bar
      app
      color="white"
      height="100"
    >
      <v-avatar
        class="mr-3"
        color="grey lighten-5"
        size="70"
      >
        <v-img
          contain
          max-height="70%"
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
        ></v-img>
      </v-avatar>

      <v-toolbar-title class="font-weight-black headline">
        VUETIFY
      </v-toolbar-title>
    </v-app-bar> -->

      <v-content>
        <section id="hero">
          <v-row no-gutters>
            <v-img
              :min-height="'calc(100vh - ' + $vuetify.application.top + 'px)'"
              max-height="100vh"
              src="./assets/hero_banner_3.jpg"
            >
              <v-theme-provider dark>
                <v-container fill-height>
                  <v-row
                    align="center"
                    class="white--text mx-auto"
                    justify="center"
                  >
                    <v-col class="white--text text-center" cols="12" tag="h1">
                      <br />
                      <span
                        :class="[
                          $vuetify.breakpoint.smAndDown
                            ? 'display-1'
                            : 'display-2',
                        ]"
                        class="font-weight-light"
                      >
                        CAMERON WHITWORTH
                      </span>

                      <br />

                      <span
                        :class="[
                          $vuetify.breakpoint.smAndDown
                            ? 'display-3'
                            : 'display-4',
                        ]"
                        class="font-weight-black"
                      >
                        PORTFOLIO
                      </span>
                    </v-col>

                    <v-btn
                      class="align-self-end"
                      fab
                      outlined
                      @click="$vuetify.goTo('#about-me')"
                    >
                      <v-icon>mdi-chevron-double-down</v-icon>
                    </v-btn>
                  </v-row>
                </v-container>
              </v-theme-provider>
            </v-img>
          </v-row>
        </section>

        <section id="about-me" class="grey lighten-2">
          <div class="py-12"></div>

          <v-container class="text-center">
            <h2 class="display-2 font-weight-bold mb-3">ABOUT ME</h2>

            <v-responsive class="mx-auto mb-8" width="56">
              <v-divider class="mb-1"></v-divider>

              <v-divider></v-divider>
            </v-responsive>

            <v-responsive
              class="mx-auto title font-weight-light mb-8"
              max-width="720"
            >
              I’m a Junior developer looking to expand my existing skills in
              creating user driven applications. I graduated from university
              with a First-Class Honours in computer science.
            </v-responsive>

            <v-avatar class="elevation-12 mb-12" size="128">
              <v-img
                src="https://media-exp1.licdn.com/dms/image/C4E03AQEm9RbsmrNBRw/profile-displayphoto-shrink_200_200/0/1629892992315?e=1640822400&v=beta&t=RRGyzv2s_VQDQdBA20Q_dp9T3P0aMlCDOEsZex3aHAo"
              ></v-img>
            </v-avatar>

            <div></div>
            <div>
              <v-btn
                class="ma-2"
                target="_blank"
                color="grey"
                href="https://www.linkedin.com/in/cameron-whitworth-997k/"
                outlined
                large
              >
                <span class="grey--text text--darken-1 font-weight-bold">
                  <v-icon
                    dark
                    left
                  >
                    mdi-linkedin
                  </v-icon>
                  LINKEDIN
                </span>
              </v-btn>
              <v-btn
                class="ma-2"
                target="_blank"
                color="grey"
                href="https://github.com/CameronWhitworth"
                outlined
                large
              >
                <span class="grey--text text--darken-1 font-weight-bold">
                  
                  <v-icon
                    dark
                    left
                  >
                    mdi-github
                  </v-icon>
                  GITHUB
                </span>
              </v-btn>
            </div>
            <div>
              <v-btn
                class="ma-2"
                target="_blank"
                color="grey"
                href="https://github.com/CameronWhitworth"
                outlined
                large
              >
                <span class="grey--text text--darken-1 font-weight-bold">
                  <v-icon
                    dark
                    left
                  >
                    mdi-file-account
                  </v-icon>
                  RESUME
                </span>
              </v-btn>
            </div>
          </v-container>

          <div class="py-12"></div>
        </section>
        <section id="skills">
          <v-parallax
            :height="$vuetify.breakpoint.smAndDown ? 1080 : 500"
            src="https://cdn.vuetifyjs.com/images/backgrounds/vbanner.jpg"
          >
            <v-container class="text-center">
              <h2 class="display-2 font-weight-bold mb-3">Technical Knowledge </h2>

              <v-responsive class="mx-auto mb-12" width="56">
                <v-divider class="mb-1"></v-divider>

                <v-divider></v-divider>
              </v-responsive>
              <v-row class="mx-auto">
                <v-col
                  v-for="[value, title] of skills"
                  :key="title"
                  cols="12"
                  md="2"
                >
                  <div class="text-center">
                    <img :src="value" height="100" width="100" />

                    <div
                      class="title font-weight-regular text-uppercase"
                      v-text="title"
                    ></div>
                  </div>
                </v-col>
              </v-row>
            </v-container>
          </v-parallax>
        </section>
        <section id="projects">
          <div class="py-12"></div>

          <v-container>
            <h2
              class="display-2 font-weight-bold mb-3 text-uppercase text-center"
            >
              Projects
            </h2>

            <v-responsive class="mx-auto mb-12" width="56">
              <v-divider class="mb-1"></v-divider>

              <v-divider></v-divider>
            </v-responsive>

            <v-row>
              <v-col
                v-for="({ src, text, title, github }, i) in projects"
                :key="i"
                cols="12"
                md="4"
              >
                <v-img
                  :src="src"
                  class="mb-4"
                  height="275"
                  max-width="100%"
                ></v-img>

                <h3
                  class="font-weight-black mb-4 text-uppercase"
                  v-text="title"
                ></h3>

                <div class="title font-weight-light mb-5" v-text="text"></div>

                <v-btn
                  class="ml-n4 font-weight-black"
                  target="_blank"
                  text
                  :href="github"
                >
                  GITHUB
                </v-btn>
              </v-col>
            </v-row>
          </v-container>

          <div class="py-12"></div>
        </section>

        <section id="features" class="grey lighten-3">
          <div class="py-12"></div>

          <v-container class="text-center">
            <h2 class="display-2 font-weight-bold mb-3">Personal Skills</h2>

            <v-responsive class="mx-auto mb-12" width="56">
              <v-divider class="mb-1"></v-divider>

              <v-divider></v-divider>
            </v-responsive>

            <v-row>
              <v-col
                v-for="({ icon, title, text }, i) in features"
                :key="i"
                cols="12"
                md="4"
              >
                <v-card class="py-12 px-4" color="grey lighten-5" flat>
                  <v-theme-provider dark>
                    <div>
                      <v-avatar color="primary" size="88">
                        <v-icon large v-text="icon"></v-icon>
                      </v-avatar>
                    </div>
                  </v-theme-provider>

                  <v-card-title
                    class="justify-center font-weight-black text-uppercase"
                    v-text="title"
                  ></v-card-title>

                  <v-card-text class="subtitle-1" v-text="text"> </v-card-text>
                </v-card>
              </v-col>
            </v-row>
          </v-container>

          <div class="py-12"></div>
        </section>

        
        
      </v-content>

      <v-footer class="justify-center" color="#292929" height="100">
        <div
          class="title font-weight-light grey--text text--lighten-1 text-center"
        >
          &copy; {{ new Date().getFullYear() }} — Cameron Whitworth
        </div>
      </v-footer>
    </v-app>
  </div>
</template>

<script>
export default {
  data() {
    return {
      projects: [
        {
          src: "https://wallpapercave.com/wp/wp2465949.png",
          title: "Flocking Algorithm ",
          text: "A recreation of the Boids flocking algorithm designed by Craig Reynolds. Project was built in JavaScript using the P5.js library and has being optimized through Quadtree implementation.",
          github: "https://github.com/CameronWhitworth/flockAI",
        },
        {
          src: "https://wallpapercave.com/wp/wp6878944.jpg",
          title: "Catalogue video games",
          text: "Tool designed for allowing users to track videos games own/played. Was built with Vue.js and the Vuetify material liberty. Connects to “RAWGs” game database API to fetch data. Users catalogue is saved to firebase.",
          github: "https://github.com/CameronWhitworth/game-tracker",
        },
        {
          src: "https://miro.medium.com/max/2000/1*oiwBIOAfbC5oN8Ml67arTQ.png",
          title: "Another Project",
          text: "Find something to add here",
          github: "https://github.com/CameronWhitworth/flockAI",
        },
      ],
      features: [
        {
          icon: "mdi-account-group-outline",
          title: "Team Player",
          text: "Extensive experience working within professional team environments.",
        },
        {
          icon: "mdi-school",
          title: "Excited To Learn",
          text: "Always looking to broaden my knowledge and learn new skills and tools.",
        },
        {
          icon: "mdi-widgets",
          title: "User Driven",
          text: "An understanding of designing applications for real users to work with.",
        },
      ],

      skills: [
        [
          "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg",
          "JavaScript",
        ],
        [
          "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vuejs/vuejs-original.svg",
          "Vue.js",
        ],
        [
          "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg",
          "Python",
        ],
        [
          "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg",
          "HTML",
        ],
        [
          "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linux/linux-original.svg",
          "Linux",
        ],
        [
          "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg",
          "Git",
        ],
      ],
    };
  },
};
</script>