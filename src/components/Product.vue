<template>

    <div class="product">

        <div :class="'product-inner ' + product.color">

            <div class="product-text-wrap">

                <h2 class="bg-text">{{ product.bgtxt }}</h2>

            </div>

            <div class="product-img-wrap">

                <img :src="product.src" class="img" />

            </div>

            <div :class="'product-detail ' + product.color">

                <h2>{{ product.title }}</h2>
                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis est minima omnis dolore tempora animi veritatis? Totam deserunt distinctio eligendi?</p>

            </div>

        </div>

    </div>

</template>

<script>
    export default {
      name: "product",
      props: ['product']
    }
</script>

<style>

    .product {
        flex: 1 1 33.333%;
        width: 100%;
        padding: 25px;
    }

    .product-inner {
        position: relative;
        padding: 25px;
        box-shadow: 0px 0px 16px rgba(0, 0, 0, 0.25);
    }

    .product-inner.terracotta {
        background-image: linear-gradient(to bottom right, #dcdde1, #ffcccc);
    }

    .product-inner.beige {
        background-image: linear-gradient(to bottom left, #dcdde1, #ced6e0 70%);
    }

    .product-inner.blue {
        background-image: linear-gradient(to bottom right, #dcdde1, #4b6584);
    }

    .product-text-wrap {
        position: absolute;
        margin-left: 1rem;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        z-index: 1;
        overflow: hidden;
    }

    .product-text-wrap h2 {
        color: #2f3542;
        font-size: 70px;
        font-weight: 800;
        opacity: 0.2;
        transform-origin: center;
        filter: drop-shadow(0px 0px 12px rgba(0, 0, 0, 0.25));
    }

    .product-img-wrap {
        transform-origin: center;
    }

    .product-img-wrap .img {
        width: 100%;
        box-shadow:
        0 12.5px 10px rgba(0, 0, 0, 0.038),
        0 100px 80px rgba(0, 0, 0, 0.07);
    }

    .product-detail {
        color: #57606f;
        opacity: 0.8;
    }

    .product-detail h2 {
        margin-top: 1rem;
        font-size: 18px;
        letter-spacing: 1px;
        font-weight: 800;
        margin-bottom: 15px;
    }

    .product-detail p {
        color: #2f3542;
        margin-top: 1rem;
        letter-spacing: 1px;
        line-height: 1.5;
        font-weight: 300;
    }


</style>