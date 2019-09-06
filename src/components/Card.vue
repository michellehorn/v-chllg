<template>
  <div class="card" :class="typeCard">
    <img v-if="image" :src="require(`../assets/images/${image}.jpg`)" alt>
    <div class="card-body">
      <h5 class="text-top">{{topText}}</h5>
      <h1 class="text-title">
        {{cardTitle}}
        <span></span>
      </h1>
      <h5 class="text-sub">{{sub}}</h5>
      <button class="btn-outline-explore" v-if="typeCard === 'dynamic'">Explore more</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: {
    typeCard: String,
    image: String,
    cardTitle: String,
    topText: String,
    sub: String
  }
};
</script>

<style lang="scss">
.card {
  width: 100%;
  height: 100%;
  background-color: #4b4545de;
  border: none;
  border-radius: 8px;
  img {
    border-radius: 8px;
    opacity: 0.65;
    width: inherit;
    height: 100%;
    object-fit: cover;
  }

  .text-top {
    text-transform: uppercase;
    font-weight: 100;
    color: white;
    font-size: 14px;
    letter-spacing: 0.2em;
    font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
      "Lucida Sans", Arial, sans-serif;
  }

  .text-sub {
    color: white;
    font-size: 16px;
    font-weight: 100;
    font-family: "Open sans", sans-serif;
  }
}

.main.card {
  max-height: 500px;
  position: relative;
  text-align: center;
  color: white;
  .card-body {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    .text-title {
      font-size: 60px;
      line-height: 10px;
      span:before {
        vertical-align: -11px;
        margin-left: -20px;
        content: "-";
      }
    }
  }
}

.dynamic.card {
  position: relative;
  max-height: 370px;
  position: relative;
  cursor: pointer;

  img {
    &:hover {
      animation-name: fadeIn;
      animation-duration: 200ms;
    }
  }
  &:hover {
    img {
      opacity: 0.4;
      filter: blur(2px);
    }
    box-shadow: 1px 2px 10px 10px #d3d3d3;
    .card-body {
      animation-name: downText;
      animation-duration: 700ms;
      top: 35%;
      .text-sub {
        padding-top: 1em;
        visibility: initial;
        animation-name: upText;
        font-size: 15px;
        animation-name: opacityOn;
        animation-duration: 2500ms;
        opacity: 1;
      }
      .btn-outline-explore {
        visibility: initial;
        animation-name: upText;
        animation-name: opacityOn;
        animation-duration: 3s;
        opacity: 1;
      }
    }
  }

  .card-body {
    z-index: 0;
    height: 50%;
    top: 60%;
    left: 50%;
    position: absolute;
    transform: translate(-50%, -50%);
    animation-name: upText;
    animation-duration: 700ms;
    .text-title {
      text-transform: uppercase;
      font-size: 30px;
      color: white;
      line-height: 0;
    }
    .text-sub,
    .btn-outline-explore {
      opacity: 0;
    }
  }
}

.btn-outline-explore {
  background-color: transparent;
  padding: 8px;
  border: 1px solid white;
  border-radius: 4px;
  color: white;
  font-weight: bold;

  &:hover {
    background-color: rgba(128, 128, 128, 0.507);
    cursor: pointer;
  }
}


// responsive
@media screen and (max-width: 500px) {
  .card {
    height: 300px;
    &.main {
      .text-title {
        font-size: 35px !important;
        span:before {
          vertical-align: -7px !important;
          margin-left: -11px !important;
          content: "-";
        }
      }
    }
  }
}
</style>
