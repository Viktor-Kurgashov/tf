<template>
  <div class="showcase-page">

    <div class="product">
      <div class="product__image-wrapper">
        <img class="product__image" src="https://images.wbstatic.net/c516x688/new/23480000/23484560-1.jpg">

        <p class="product__discount">-10%</p>

        <button class="product__view-btn">Быстрый просмотр</button>
      </div>

      <div class="product__prices">
        <p class="product__price1">31 491 &#8381;</p>
        <p class="product__price2">34 990 &#8381;</p>
        <p class="product__price3">30 861 &#8381;</p>
      </div>

      <p class="product__params">Samsung / Смартфон Galaxy A52 / 6.5" / 1080x2400 / Super AMOLED / 8 ГБ / 256 ГБ / 4500 мА*ч</p>

      <div class="product__raiting">
        <img class="product__star" src="@/assets/star-fill.svg">
        <img class="product__star" src="@/assets/star-fill.svg">
        <img class="product__star" src="@/assets/star-fill.svg">
        <img class="product__star" src="@/assets/star-fill.svg">
        <img class="product__star" src="@/assets/star-fill.svg">

        <p class="product__rewiews">87</p>
      </div>

      <p class="product__credit">РАССРОЧКА 0-0-6</p>

      <div class="product__buttons">
        <button class="product__buy-btn">В корзину</button>

        <button class="product__like-btn">
          <img class="product__like-btn-icon" src="@/assets/heart.svg">
        </button>
      </div>
    </div>



    <div class="product">
      <div class="product__image-wrapper">
        <img class="product__image" src="https://images.wbstatic.net/c516x688/new/23480000/23484560-1.jpg">

        <p class="product__discount">-10%</p>

        <button class="product__view-btn">Быстрый просмотр</button>
      </div>

      <div class="product__prices">
        <p class="product__price1">31 491 &#8381;</p>
        <p class="product__price2">34 990 &#8381;</p>
        <p class="product__price3">30 861 &#8381;</p>
      </div>

      <p class="product__params">Samsung / Смартфон Galaxy A52 / 6.5" / 1080x2400 / Super AMOLED / 8 ГБ / 256 ГБ / 4500 мА*ч</p>

      <div class="product__raiting">
        <img class="product__star" src="@/assets/star-fill.svg">
        <img class="product__star" src="@/assets/star-fill.svg">
        <img class="product__star" src="@/assets/star-fill.svg">
        <img class="product__star" src="@/assets/star-fill.svg">
        <img class="product__star" src="@/assets/star-fill.svg">

        <p class="product__rewiews">87</p>
      </div>

      <p class="product__credit">РАССРОЧКА 0-0-6</p>

      <div class="product__buttons">
        <button class="product__buy-btn">В корзину</button>

        <button class="product__like-btn">
          <img class="product__like-btn-icon" src="@/assets/heart.svg">
        </button>
      </div>
    </div>



    <div class="product">
      <div class="product__image-wrapper">
        <img class="product__image" src="https://images.wbstatic.net/c516x688/new/23480000/23484560-1.jpg">

        <p class="product__discount">-10%</p>

        <button class="product__view-btn">Быстрый просмотр</button>
      </div>

      <div class="product__prices">
        <p class="product__price1">31 491 &#8381;</p>
        <p class="product__price2">34 990 &#8381;</p>
        <p class="product__price3">30 861 &#8381;</p>
      </div>

      <p class="product__params">Samsung / Смартфон Galaxy A52 / 6.5" / 1080x2400 / Super AMOLED / 8 ГБ / 256 ГБ / 4500 мА*ч</p>

      <div class="product__raiting">
        <img class="product__star" src="@/assets/star-fill.svg">
        <img class="product__star" src="@/assets/star-fill.svg">
        <img class="product__star" src="@/assets/star-fill.svg">
        <img class="product__star" src="@/assets/star-fill.svg">
        <img class="product__star" src="@/assets/star-fill.svg">

        <p class="product__rewiews">87</p>
      </div>

      <p class="product__credit">РАССРОЧКА 0-0-6</p>

      <div class="product__buttons">
        <button class="product__buy-btn">В корзину</button>

        <button class="product__like-btn">
          <img class="product__like-btn-icon" src="@/assets/heart.svg">
        </button>
      </div>
    </div>

  </div>
</template>



<style>
.showcase-page {
  display: flex;
  flex-flow: row wrap;
  justify-content: space-between;
}

.product {
  flex-basis: 32%;
  border-radius: 20px;
  padding: 10px 20px 30px;
}
.product:hover {
  box-shadow: 0px 0px 8px 0px lightgrey;
}



@media screen and (max-width: 800px) {
  .product {
    flex-basis: 48%;
    margin-bottom: 16px;
  }
}

@media screen and (max-width: 540px) {
  .showcase-page {
    justify-content: center;
  }
  .product {
    flex-basis: 90%;
    margin-bottom: 16px;
  }
}



.product__image-wrapper {
  position: relative;
  padding: 0 2px;
  font-size: 0;
}
.product__image {
  width: 100%;
  height: auto;
}

.product__discount,
.product__view-btn {
  position: absolute;
  font-size: 1rem;
}

.product__discount {
  border-radius: 12px;
  background: #fde8f9;
  color: #cb11ab;
  left: 0;
  bottom: 12px;
  height: 25px;
  line-height: 25px;
  padding: 0 8px;
}

.product__view-btn {
  visibility: hidden;
  background: rgba(230, 230, 230, 0.8);
  border-radius: 22px;
  left: calc(50% - 90px);
  top: calc(50% - 22px);
  width: 180px;
  height: 45px;
  line-height: 47px;
}
.product__image-wrapper:hover > .product__view-btn {
  visibility: visible;
}



.product__prices {
  font-weight: bold;
  display: flex;
  flex-flow: row wrap;
  align-items: center;
  font-size: 18px;
  line-height: 18px;
}
.product__price1 {
  font-size: 24px;
  line-height: 24px;
}
.product__price2 {
  text-decoration: line-through;
  text-decoration-thickness: 2px;
  margin-left: 10px;
  color: grey;
}
.product__price3 {
  flex-basis: 100%;
  margin-top: 8px;
  color: #cb11ab;
}



.product__raiting {
  display: flex;
  height: 20px;
}
.product__star:not(.product__star:first-child) {
  margin-left: 4px;
}
.product__rewiews {
  margin-left: 8px;
  padding-top: 4px;
  line-height: 16px;
  color: grey;
}



.product__params {
  margin: 10px 0;
  line-height: 21px;
  color: grey;
}

.product__credit {
  background-image: linear-gradient(to right, greenyellow, yellow);
  border-radius: 20px;
  font-size: 18px;
  width: 190px;
  text-align: center;
  height: 40px;
  line-height: 42px;
  margin: 15px 0;
}



.product__buttons {
  display: flex;
  height: 45px;
}

.product__buy-btn {
  border-radius: 12px;
  background: #cb11ab;
  color: white;
  font-size: 1rem;
  font-weight: bold;
  line-height: 45px;
  width: 140px;
}
.product__buy-btn:active {
  transform: scale(98%);
}

.product__like-btn {
  font-size: 0;
  width: 45px;
  margin-left: 10px;
}
.product__like-btn-icon {
  width: 27px;
  height: auto;
}

</style>
