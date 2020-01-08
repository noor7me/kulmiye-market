<template>
  <v-container fluid>
    <v-row>
      <v-col>
        <v-row justify="center">
          <div class="product-box"
            :class= "{'product-box-mobile' : ($vuetify.breakpoint.xsOnly || $vuetify.breakpoint.smOnly) }"
            v-for="product in products"
            :key="product.id"
          >
            <v-img
              
              :src= product.image
          
              contain
              aspect-ratio="1"

            >
            </v-img>
            <div class="product-title"
              :class= "{'product-title-mobile' : ($vuetify.breakpoint.xsOnly || $vuetify.breakpoint.smOnly) }"
            >
              {{product.title}}
            </div>
          </div>
        </v-row>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
// @ is an alias to /src


export default {
  name: "home",
  components: {
   
  },
  data() {
    return {
        products: [
          {
            id: 1,
            title: "You name it",
            description: "you describe it....",
            image: "images/sampleImages/dhiilo.JPG"
          },
          {
            id: 2,
            title: "AbdiAziz.. Please name this ",
            description: "you describe it....",
            image: "images/sampleImages/honey.jpg"
          },
          {
            id: 3,
            title: "You name it",
            description: "you describe it....",
            image: "images/sampleImages/books.JPG"
          },
          {
            id: 4,
            title: "You name it",
            description: "you describe it....",
            image: "images/sampleImages/laptob.JPG"
          },

          {
            id: 5,
            title: "You name it",
            description: "you describe it....",
            image: "images/sampleImages/travel.JPG"
          },
          {
            id: 6,
            title: "you name it",
            description: "you describe it....",
            image: "images/sampleImages/sofa.JPG"
          },

          {
            id: 7,
            title: "you name it",
            description: "you describe it....",
            image: "images/sampleImages/bed.JPG"
          },

          {
            id: 8,
            title: "you name it",
            description: "you describe it....",
            image: "images/sampleImages/launchTable.JPG"
          },

          {
            id: 9,
            title: "you name it",
            description: "you describe it....",
            image: "images/sampleImages/cofeecup.jpg"
          },
          {
            id: 10,
            title: "I am sure you can name it!!!",
            description: "you describe it....",
            image: "images/sampleImages/xarig.JPG"
          },

          {
            id: 11,
            title: "you name it",
            description: "you describe it....",
            image: "images/sampleImages/pleated.JPG"
          },

          {
            id: 12,
            title: "you name it",
            description: "you describe it....",
            image: "images/sampleImages/shoe.JPG"
          },

          {
            id: 13,
            title: "you name it",
            description: "you describe it....",
            image: "images/sampleImages/beauty.JPG"
          },

          {
            id: 14,
            title: "you name it",
            description: "you describe it....",
            image: "images/sampleImages/uw.jpg"
          },
          {
            id: 15,
            title: "you name it",
            description: "you describe it....",
            image: "images/sampleImages/farming.jpg"
          },

          {
            id: 16,
            title: "you name it",
            description: "you describe it....",
            image: "images/sampleImages/car.JPG"
          },

          {
            id: 17,
            title: "What about this one? !!",
            description: "you describe it....",
            image: "images/sampleImages/tesla.jpg"
          },

          {
            id: 18,
            title: "you name it",
            description: "you describe it....",
            image: "images/sampleImages/TV.JPG"
          },
        ]
    }
  }
};
</script>

<style  scoped>
  .product-box{
    width: 260px;
    height: 360px;
    margin-top: 25px;
    margin-right: 10px;
    margin-left: 10px;
    border-radius: 25px;
    background-color: white;
    box-shadow: 0 1px 1px 0 rgba(0, 160, 35, 0.4), 0 1px 15px 0 rgba(0, 0, 0, 0.19);
  }

  .product-box-mobile{
    width: 166px;
    height: 240px;
    margin-top: 15px;
    margin-right: 6px;
    margin-left: 6px;
    background-color: white;
  }
  .product-title{
    text-align: center;
    font-size: 24px;
    font-style: italic;
    font-family: monospace;
    color: grey;
    font-weight: 600
  }

  .product-title-mobile{
    text-align: center;
    font-size: 18px;
    font-style: italic;
    font-family: monospace;
    color: grey;
    font-weight: 300
  }
</style>