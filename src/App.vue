<template>

  <main id="app" @mousemove="mousemove">

    <section class="products">

      <Product 
        v-for="product in products"
        :key="product.color"
        :product="product"
      />

    </section>

  </main>

</template>

<script>
import Product from './components/Product.vue'

export default {
  name: 'App',
  components: {
    Product
  },
  data() {
    return {
      products: [
        {
          title: "Bougie Vegan - Slow North",
          desc: "Geranium + Rose",
          color: "terracotta",
          bgtxt: "Bonne",
          src: require("./assets/candle3.jpg")
        },
        {
          title: "Bougie Vegan - Slow North",
          desc: "Eucalyptus + Lavande",
          color: "beige",
          bgtxt: "Fête",
          src: require("./assets/candle2.jpg")
        },
        {
          title: "Bougie Vegan - Slow North",
          desc: "Cigtronnelle + Mandarine",
          color: "blue",
          bgtxt: "Maman.",
          src: require("./assets/candle1.jpg")
        }
      ]
    }
  }, 
  methods: {
    mousemove (e) {
      let mouseX = e.clientX;
      let mouseY = e.clientY;

      let products = document.querySelectorAll('.products .product');

      for (let i = 0; i < products.length; i++) {
        let product = products[i];

        let product_image = product.querySelector('.product-img-wrap');

        let img_x = mouseX - this.coords(product_image).x;
        let img_y = mouseY - this.coords(product_image).y;

        product_image.style.transform = `translateY(-${img_y/45}px) translateX(-${img_x/45}px)`;

        let bgText = product.querySelector('.bg-text');
        let bg_x = mouseX - this.coords(bgText).x;
        let bg_y = mouseY - this.coords(bgText).y;
        bgText.style.transform = `translateX(${bg_x/25}px) translateY(${bg_y/25}px)`;
      
      }
    },
    coords (element) {
      let coords = element.getBoundingClientRect();

      return {
        x: coords.left / 2,
        y: coords.top / 2
      }
    }
  }
}
</script>

<style>

  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  body {
    font-family: "Helvetica Neue", sans-serif;
  }

  main {
    width: 100vw;
    min-height: 100vh;
    /* overflow: hidden; */
    background-color: #eee;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .products {
    display: flex;
    max-width: 1280px;
    padding: 25px;
    margin: 0 auto;
  }


</style>
