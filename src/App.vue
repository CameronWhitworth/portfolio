<template>
  <div id="app">
    <v-app>
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
              with a <b> First-Class Honours </b> in computer science.
            </v-responsive>

            <v-avatar class="elevation-12 mb-12" size="128">
              <v-img
                src="./assets/pfp_port.jpeg"
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
                width="140"
              >
                <span class="grey--text text--darken-1 font-weight-bold">
                  <v-icon dark left> mdi-linkedin </v-icon>
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
                width="140"
              >
                <span class="grey--text text--darken-1 font-weight-bold">
                  <v-icon dark left> mdi-github </v-icon>
                  GITHUB
                </span>
              </v-btn>
            </div>
            <div>
              <v-btn
                class="ma-2"
                target="_blank"
                color="grey"
                href="https://github.com/CameronWhitworth/portfolio/blob/main/Resume.pdf"
                outlined
                large
                width="140"
              >
                <span class="grey--text text--darken-1 font-weight-bold">
                  <v-icon dark left> mdi-file-account </v-icon>
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
              <h2 class="display-2 font-weight-bold mb-3">
                Technical Knowledge
              </h2>

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
                    <img :src="value" :height="$vuetify.breakpoint.smAndDown ? 85 : 100" />

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

      <v-footer class="justify-center" color="#292929" height="140">
        <div
          class="title font-weight-light grey--text text--lighten-1 text-center"
        >
          &copy; {{ new Date().getFullYear() }} — Cameron Whitworth

          <br />

          <v-btn
            class="ma-1"
            target="_blank"
            color="transparent"
            plain
            href="https://www.linkedin.com/in/cameron-whitworth-997k/"
          >
            <span class="grey--text text--darken-1 font-weight-bold">
              <v-icon dark> mdi-linkedin </v-icon>
            </span>
          </v-btn>
          <v-btn
            class="ma-1"
            target="_blank"
            color="transparent"
            plain
            href="https://github.com/CameronWhitworth"
          >
            <span class="grey--text text--darken-1 font-weight-bold">
              <v-icon dark> mdi-github </v-icon>
            </span>
          </v-btn>
          <v-btn
            class="ma-1"
            target="_blank"
            color="transparent"
            plain
            href="https://github.com/CameronWhitworth"
          >
            <span class="grey--text text--darken-1 font-weight-bold">
              <v-icon dark> mdi-file-account </v-icon>
            </span>
          </v-btn>
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
          // src: "https://miro.medium.com/max/2000/1*oiwBIOAfbC5oN8Ml67arTQ.png", c++ image
          src: "https://www.koenvanzeijl.nl/blogs/blog-with-vue-nuxt/header.jpeg",
          title: "Maximalist",
          text: "Site designed to showcase maximalism design, artwork, decor and artists. Static site is made with Nuxt.js and connected to the contentful headless CMS.",
          github: "https://github.com/CameronWhitworth/maximalist",
        },
        {
          src: "https://wallpapercave.com/wp/wp2465949.png",
          title: "Flocking Algorithm ",
          text: "A recreation of the Boids flocking algorithm designed by Craig Reynolds. Project was built in JavaScript using the P5.js library and has being optimized through a Quadtree implementation.",
          github: "https://github.com/CameronWhitworth/flockAI",
        },
        {
          src: "https://wallpapercave.com/wp/wp6878944.jpg",
          title: "Catalogue video games",
          text: "Tool designed for allowing users to track videos games own/played. Was built with Vue.js and the Vuetify material liberty. Connects to “RAWGs” game database API to fetch data. Users catalogue is saved to firebase.",
          github: "https://github.com/CameronWhitworth/game-tracker",
        },
      ],
      features: [
        {
          icon: "mdi-account-group-outline",
          title: "Team Player",
          text: "Extensive experience working with and within professional team environments.",
        },
        {
          icon: "mdi-school",
          title: "Excited To Learn",
          text: "Always looking to broaden my knowledge and learn new skills and industry tools.",
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