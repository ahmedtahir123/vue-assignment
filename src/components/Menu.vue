<template>
     <v-toolbar
      color="#7bae23"
      dark
      flat
    >
      <v-tabs
          v-model="tab"
          align-with-title
        >
          <v-tabs-slider color="yellow"></v-tabs-slider>

          <v-tab
            v-for="item in items"
            :key="item"
          >
            {{ item }}
          </v-tab>
        </v-tabs>
     </v-toolbar>
</template>

<script>

export default {
  name: 'Menu',
  components: {
  },

  data: () => {
   return {
        tab: null,
        items: [
          'BEAUTY & PERSONAL CARE', ' HOUSEHOLD', 'GROCERY', 'HOME NEEDS', 'TOYS', 'PHARMACY', 'MORE'
        ],
      }
  },
};
</script>
