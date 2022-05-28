<template>
  <!-- Women Banner Section Begin -->
  <section class="women-banner spad">
    <div class="container-fluid">
      <div class="row">
        <div class="col-lg-12 mt-5" v-if="products.length > 0">
          <carousel class="product-slider" :nav="false" :autoplay="true" :dots="false">
            <div class="product-item" v-for="itemProduct in products" :key="itemProduct.id">
              <div class="pi-pic">
                <img :src="itemProduct.galleries[0].photo" alt="" class="mickey-img"/>
                <ul>
                  <li class="w-icon active">
                    <a href="#"><i class="icon_bag_alt"></i></a>
                  </li>
                  <li class="quick-view">
                    <router-link :to="'/product/' + itemProduct.id">+ Quick View</router-link>
                    <!-- <a href="product.html">+ Quick View</a> -->
                  </li>
                </ul>
              </div>
              <div class="pi-text">
                <div class="catagory-name">{{ itemProduct.type }}</div>
                <a href="#">
                  <h5>{{ itemProduct.name }}</h5>
                </a>
                <div class="product-price">
                  ${{ itemProduct.type }}
                  <span>$35.00</span>
                </div>
              </div>
            </div>
          </carousel>
        </div>
        <div class="col-lg-12" v-else>
          Produk belum tersedia
        </div>
      </div>
    </div>
  </section>
  <!-- Women Banner Section End -->
</template>

<script>
import carousel from "vue-owl-carousel";
import axios from "axios"
export default {
  name: "ProductShayna",
  components: {
    carousel,
  },
  data () {
    return {
      products: []
    }
  },
  mounted() {
    axios
    .get("http://shayna.backend.test/api/products")
    .then(res => (this.products = res.data.data.data))
    .catch(err => console.log(err));
  }
};
</script>

<style scoped>
  .product-item {
    margin-right: 25px;
  }
  .mickey-img {
    max-height: 500px
  }
</style>