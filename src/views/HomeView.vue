<template>
  <div class="home">
    <HeaderShayna />
    <HeroShayna />
    <ProductShayna />
    <InstaShayna />
    <PartnerShayna />
    <FooterShayna />
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import HeaderShayna from '@/components/HeaderShayna.vue'
import HeroShayna from '@/components/HeroShayna.vue'
import ProductShayna from '@/components/ProductShayna.vue'
import InstaShayna from '@/components/InstaShayna.vue'
import PartnerShayna from '@/components/PartnerShayna.vue'
import FooterShayna from '@/components/FooterShayna.vue'

export default {
  name: 'HomeView',
  components: {
    HeaderShayna,
    HeroShayna,
    ProductShayna,
    InstaShayna,
    PartnerShayna,
    FooterShayna
  }
}
</script>
