<template>
  <div id="app">
    <div class="container">
      <div class="card" v-for="cardProd in cardProds">
        <span class="country"> {{cardProd.country}}</span>
        <div class="card-img">
          <img v-for="imgItem in cardProd.img" :src="(require(`${imgItem}`))" alt="">
        </div>
        <div class="card-info-prod">
          <div class="card-info">
            <span class="star"><i class="fa fa-star" aria-hidden="true"></i></span>
            <span class="title">{{cardProd.title}}</span>
            <span class="heart" v-if="cardProd.like"><i class="fa fa-heart" aria-hidden="true"></i></span>
            <span class="heart" v-else><i class="far fa-heart" aria-hidden="true"></i></span>
          </div>

          <div class="price">
            <span>{{cardProd.price}}</span>
            <button class="btn-cart">В корзину</button>
          </div>

        </div>
      </div>


      <div class="card-phone">
        <p>Просмотр в 360°</p>
        <vue-three-sixty
            :amount=5
            imagePath="./iPhone"
            fileName="iPhone-{index}.jpg"
        />
        <div class="card-info-prod">
          <div class="card-info">
            <span class="star"><i class="fa fa-star" aria-hidden="true"></i></span>
            <span class="title">iPhone</span>
            <span class="heart"><i class="fa fa-heart" aria-hidden="true"></i></span>
          </div>

          <div class="price">
            <span>5 000 $</span>
            <button class="btn-cart">В корзину</button>
          </div>

        </div>
      </div>
    </div>
  </div>
</template>

<script>


export default {
  name: 'App',
  data() {
    return {
      cardProds: [
        {
          name: 'car',
          img: ['./assets/img/car/carRed.jpg'],
          country: 'USA',
          title: 'Chevrolet Corvette',
          like: false,
          price: '120 000 $'
        },
        {
          name: 'computer',
          img: ['./assets/img/computer/pc.jpg'],
          country: 'Germany',
          title: ' Top PC',
          like: false,
          price: '1 000 $'
        },
        {
          name: 'tv',
          img: ['./assets/img/tv/tvSamsung.jpg'],
          country: 'China',
          title: 'TV Samsung',
          like: true,
          price: '500 $'
        },

        {
          name: 'bike',
          img: ['./assets/img/bike/bmw-g-310-r.jpg'],
          country: 'Germany',
          title: 'BMW bike',
          like: false,
          price: '3 000 $'

        },
        {
          name: 'coffeeMachine',
          img: ['./assets/img/coffeeMachine/2c1168de25a1d7324cb2025f14261704.jpg'],
          country: 'Romania',
          title: 'Coffee machine Magnifica',
          like: false,
          price: '700 $'
        },
        {
          name: 'headphones',
          img: ['./assets/img/headphones/orig.jpg'],
          country: 'China',
          title: 'Headphones Sony',
          like: false,
          price: '300 $'
        },
        {
          name: 'keyboard',
          img: ['./assets/img/keyboard/hyperx1.jpg'],
          country: 'China',
          title: 'Keyboard HyperX',
          like: false,
          price: '100 $'
        },
        {
          name: 'mouse',
          img: ['./assets/img/mouse/dd641a3e910b0e1d4bd7e5d55ba64e0a.jpg'],
          country: 'China',
          title: 'Computer mouse',
          like: false,
          price: '100 $'
        },
        {
          name: 'robot',
          img: ['./assets/img/robot/depositphotos_1559329-stock-photo-funny-robot-stay-and-show.jpg'],
          country: 'Japan',
          title: 'Jolly robot ',
          like: false,
          price: '5 000 $'
        },
        {
          name: 'yacht',
          img: ['./assets/img/yacht/Bez-imeni.jpg'],
          country: 'Russia',
          title: 'Luxury yacht',
          like: false,
          price: '120 000 000 $'
        },
      ]
    }
  },


}
</script>

<style>
.container {
  display: flex;
  align-items: center;
  justify-content: space-around;
  width: 50vw;
  flex-wrap: wrap;
  margin: 0 auto;

}

.card {
  border: 1px solid rebeccapurple;
  max-width: 300px;
  height: 250px;
  margin: 10px 0;
}

.card .card-img {
  width: 100%;
  height: 155px;
}

.card img {
  width: 100%;
  height: 100%;
  object-fit: contain;
  object-position: center;
}
.country {
  font-size: 12px;
  color: #726c6c;
  padding: 0 0 0 5px;
}

.card-info-prod {
  display: flex;
  flex-direction: column;
  height: 15%;
}

.card-info {
  padding: 5px 5px 0 5px;
  display: flex;
  justify-content: space-between;
  margin: auto 0;
}

.card-info .star {
  color: yellow;
  opacity: 0;
}
.card-info .title {
  text-align: center;
  color: white;
  opacity: 0;
}

.card-info .heart {
  color: #DF3A76;
  opacity: 0;
}

.price {
  display: flex;
  justify-content: space-between;
  margin: auto 0;
  padding: 0 5px 0 5px;
  color: #000;
}

.btn-cart {
  background-color: #8b63be;
  border-radius: 3px;
  color: #fff;
}

.card:hover .card-info-prod {
  background: #303030bd;
  height: 31%;
}

.card:hover .star {
  opacity: 1;
}
.card:hover .title {
  opacity: 1;
}

.card:hover .heart {
  opacity: 1;
}

.card:hover .price {
  color: #fff
}

.card-phone {
  border: 1px solid rebeccapurple;
  max-width: 300px;
  height: 100%;
  margin: 10px 0;
}

.card-phone:hover .card-info-prod {
  background: #303030bd;
  height: 31%;
}

.card-phone:hover .star {
  opacity: 1;
}
.card-phone:hover .title {
  opacity: 1;
}

.card-phone:hover .heart {
  opacity: 1;
}

.card-phone:hover .price {
  color: #fff
}

.v360-viewer-container {
  max-width: 300px;
  height: 250px;
  margin: 10px 0;
}

.v360-image-container {
  width: 100%;
  height: 100%;
  object-fit: contain;
  object-position: center;
}

#v360-menu-btns {
  display: none!important;
}
</style>




