<template>
  <v-container>
    <v-row class="text-center">
     <Menu/>
    </v-row>
    <v-row class="text-center">
     <v-carousel cycle :show-arrows="true">
    <v-carousel-item
      v-for="(item,i) in items"
      :key="i"
      :src="item.src"
    ></v-carousel-item>
  </v-carousel>
  </v-row>
  <v-row class="text-center">
   <h1 id="heading">Categories</h1>
  </v-row>
  

  <v-row   class="text-center">
  <v-card
    :loading="loading"
    class="mx-auto my-12"
    max-width="374"
    v-for="item in cardsData"
    :key="item"
  >
    <template slot="progress">
      <v-progress-linear
        color="deep-purple"
        height="10"
        indeterminate
      ></v-progress-linear>
    </template>

    <v-img
      height="250"
      :src="item.src"
    ></v-img>

    <v-card-text>
      <v-row
        align="center"
        class="mx-0"
      >
        <v-rating
          :value="4.5"
          color="amber"
          dense
          half-increments
          readonly
          size="14"
        ></v-rating>

        <div class="grey--text ms-4">
          {{item.rating}}
        </div>
      </v-row>

      <div class="my-4 text-subtitle-1">
        
      </div>

      <div>{{item.desc}}</div>
    </v-card-text>

   
  </v-card>
</v-row>
  </v-container>
      

</template>

<script>
import Menu from './Menu';

  export default {
    name: 'HelloWorld',
    data: () => ({
       loading: false,
       selection: 1,
       items: [
          {
            src: 'https://hummart.com/media/wysiwyg/sliders/will-be-back-banner.jpg',
          },
          {
            src: 'https://hummart.com/media/wysiwyg/sliders/will-be-back-banner.jpg',
          },
          {
            src: 'https://hummart.com/media/wysiwyg/sliders/will-be-back-banner.jpg',
          },
          {
            src: 'https://hummart.com/media/wysiwyg/sliders/will-be-back-banner.jpg',
          },
        ],
        cardsData: [
          {
            src: 'https://hummart.com/media/wysiwyg/CategoryBanners/meat_seafood_new.jpg',
            rating:5.0,
            desc:"watch"
          },
          {
            src: 'https://hummart.com/media/wysiwyg/CategoryBanners/beverages-250x234.jpg',
          rating:5.0,
            desc:"watch"
          },
          {
            src: 'https://hummart.com/media/wysiwyg/CategoryBanners/biscuits-250x234.jpg',
          rating:5.0,
            desc:"watch"
          },

          {
            src: 'https://hummart.com/media/wysiwyg/CategoryBanners/noodles-sauses-and-frozen-food-250x234.jpg',
          rating:5.0,
            desc:"watch"
          },
          {
            src: 'https://hummart.com/media/wysiwyg/CategoryBanners/noodles-sauses-and-frozen-food-250x234.jpg',
          rating:5.0,
            desc:"watch"
          },
        ],
    }),
    methods: {
      reserve () {
        this.loading = true

        setTimeout(() => (this.loading = false), 2000)
      },
    },
    components: {
      Menu
  },
  }
</script>

<style>
#heading {
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  margin-bottom: 60px;

}
</style>
