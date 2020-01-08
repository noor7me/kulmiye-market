<template>
    <div>
        <v-app-bar
            app
            dark
            color="primary"
            dense
            flat
        >
            <v-app-bar-nav-icon
                @click.stop="drawer = !drawer" 
                color="secondary"
                v-show="!searchOn && !drawer"
            >
            </v-app-bar-nav-icon>

              <div>
                  <v-img
                     
                      alt="QAMAAR Logo"
                      class="shrink mr-2"
                      contain
                      src="logo.JPG"
                      transition="scale-transition"
                      width="24"
                      
                  />
              </div>
                <v-spacer></v-spacer>
                <v-text-field
                      class="search-box"
                      v-show="searchOn"
                      v-model="message"
                      outlined
                      filled
                      autofocus
                      solo-inverted
                      dense
                      flat
                      clearable
                      label="ka raadi suuqa kulmiye"
                      type="text"
                      color="secondary"
                      prepend-inner-icon="mdi-magnify"
                  >

                </v-text-field>
         
            <div class="my-2"> 
              <v-btn
                v-show="searchOn"
                tile
                color="primary black--text"
                elevation = "0"
                depressed
                exact
                width="10px"
                height="40px"
                @click="closeSearch()"
                >
                <span class="cancel-text secondary--text">Cancel</span>
                
              </v-btn> 
              </div>           
            <div v-show="!searchOn">
              <v-btn icon>
                  <v-icon color="secondary"
                    @click="closeSearch()"
                  >mdi-magnify</v-icon>
              </v-btn>
            <v-btn icon>
                <v-icon color="secondary">mdi-camera</v-icon> 
              <span class="secondary--text">iibi</span>
            </v-btn>
            <div class="iibgee-box">

            </div>

            </div>
        </v-app-bar>

        <v-navigation-drawer  
              v-model="drawer"
              width="960"
              app     
            >
            <div   class="mdi-alpha-box">
              <v-icon
                size="30"
                color="secondary"
                @click="closeDrawer()"
               
              >mdi-alpha-x-box-outline</v-icon>
            </div>
            <v-spacer></v-spacer>

            <div class="drawer-box"
            >       
                <v-row justify="center">
                  <v-col cols="12"
          
                  >
                  <v-row
                    justify="center"
                  >
                      <div
                        v-for="scarf in scarfs"
                        :key="scarf.id"
                        class="card-box"
                      >
                        <v-img
                          :src=scarf.image
                          width="200"
                          height="200"
                          aspect-ratio="2.6"
                          contain
                        
                        ></v-img>
                        <div class="scarf-title">
                          {{scarf.title}}
                        </div>
                      </div>

                      </v-row>
                  </v-col>
                </v-row>

                
        </div>
      </v-navigation-drawer>
      
    </div>
</template>

<script>
  export default {
    name: 'mobileHeader',
    data() {
      return{
        drawer: false,
        group: false,

        searchOn: false,
        message: "",

        scarfs: [
          {
            id: 1,
            title: "Electronics",
            describtion: "2020 newly designed scarf",
            image:    "images/electronics.JPG"

          },

          {
            id: 2,
            title: "Gawaari",
            describtion: "2020 newly designed scarf",
            image:    "images/cars.JPG"
          },

          
          {
            id: 3,
            title: "Alaabta Guryaha",
            describtion: "2020 newly designed scarf",
            image:    "images/furniture.JPG"
          },


          {
            id: 4,
            title: "you name it",
            describtion: "2020 newly designed scarf",
            image:    "images/youname1.JPG"
          },

    

            {
            id: 5,
            title: "you name it",
            describtion: "2020 newly designed scarf",
            image:    "images/youname2.JPG"
          },

          {
            id: 6,
            title: "you name it",
            describtion: "2020 newly designed scarf",
            image:    "images/youname3.JPG"
          },
        ]
      }
    },

  methods: {
    closeSearch() {
      this.searchOn = !this.searchOn    //exit search mode
    },
    closeDrawer() {
      this.drawer = !this.drawer;
    }
  },

  }
</script>

<style scoped>
  .search-box{
    margin-top: 28px;
    margin-right: 10px;
    width: 240px;
  }
  .cancel-text{     
    font-size: 10px;
    font-style: normal;
  }
  .drawer-box{
    margin-top: 40px;
  }
  .mdi-alpha-box{
   
    margin-top: 10px;
    margin-left: 10px;
  }
  .logo-box{
    margin-left: 25px;
  }
  .product-box{
    margin-top: 40px;
    background-color: blue;
    width: 100px;
    height: 100px;
  }
  .card-box{
    margin-top: 25px;
    margin-right: 10px;
    margin-left: 10px;
    border-radius: 25px;

    box-shadow: 0 1px 1px 0 rgba(0, 160, 35, 0.4), 0 1px 15px 0 rgba(0, 0, 0, 0.19);
    width: 160px;
    height: 270px;
  }

  .card-box:hover{
    transform: scale(1.05);
    box-shadow: 0 3px 12px 0 rgba(0, 160, 35, 0.4), 0 1px 15px 0 rgba(0, 0, 0, 0.19);
    border-color: #39b982;
    
  }
  .footer-box{
    margin-top: 60px;
  }
  .scarf-title{
    text-align: center;
    font-size: 24px;
    font-style: italic;
    font-family: monospace;
    color: grey;

    font-weight: 600;
    

  }

</style>