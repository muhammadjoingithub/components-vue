<template>
 <div class="app">
     <DropdownMenu />
     <CButton/>
     <sliderImage/>
     <CountryProps :items="boxesItems" />
 </div>

</template>

<script>
import CButton from './components/CButton.vue'
import DropdownMenu from './components/DropdownMenu.vue'
import sliderImage from './components/sliderImage.vue'
import CountryProps from './components/CountryProps.vue'





export default {
  name: 'App',
  components: {
    CButton,
    DropdownMenu,
    sliderImage,
    CountryProps
  },
   data() {
    return {
      boxesItems: [
        {
          image: '../assets/vue11.png',
          alt: 'Изображение 1',
          title: 'Turkmenistan',
          description: '17 destinations'
        },
        {
          image: '../assets/vue22.png',
          alt: 'Изображение 2',
          title: 'Azerbaijan',
          description: '21 destinations'
        },
        {
          image: '../assets/vue33.png',
          alt: 'Изображение 3',
          title: 'Türkiye',
          description: '20 destinations'
        },
      ]
    };
  }
}
</script>

<style>

</style>
