<script>
export default {
  name: "Card",
  props:{
    name: String,
    type: String,
    img: Array
  }
}
</script>

<template>
  <div class="col mb-5">
    <div class="ms-card text-center">
      <div class="ms-card-img">
        <img class="w-100" :src="img[0].image_url" :alt="name">
      </div>
      <div class="ms-card-info d-flex p-3 flex-column justify-content-between">
        <span class="text-white ms-name">{{name}}</span>
        <span class="ms-type">{{type}}</span>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
  .col{
    cursor: pointer;

    .ms-card{
      box-shadow: 0 0 .3rem lighten($color: #000000, $amount: 10);
      background-color: #D48F38;

      .ms-card-img:hover img{
        transform: scale(.95);
      }

      .ms-card-info{
        height: 8rem;

        .ms-name{
          font-size: .9rem;
          text-transform: uppercase;
        }

        .ms-type{
          font-size: .8rem;
          font-weight: bold;
        }
      }
    }
  }
</style>