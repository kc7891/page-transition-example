<template>
  <div class="VueToNuxtLogo" :class="{orange: isOrange, pink: isPink}">
    <div class="Triangle Triangle--two"/>
    <div class="Triangle Triangle--one"/>
    <div class="Triangle Triangle--three"/>
    <div class="Triangle Triangle--four"/>
  </div>
</template>

<script>
export default {
  props: {
    colorType: String
  },
  computed: {
    isOrange() {
      return this.colorType === "orange"
    },
    isPink() {
      return this.colorType === "pink"
    }
  }
}
</script>

<style>
.VueToNuxtLogo {
  display: inline-block;
  animation: turn 1s linear forwards 0.5s;
  transform: rotateX(180deg);
  position: relative;
  overflow: hidden;
  height: 180px;
  width: 245px;
}

.Triangle {
  position: absolute;
  top: 0;
  left: 0;
  width: 0;
  height: 0;
}

.Triangle--one {
  border-left: 105px solid transparent;
  border-right: 105px solid transparent;
  border-bottom: 180px solid #41b883;
}

.Triangle--two {
  top: 30px;
  left: 35px;
  animation: goright 0.3s linear forwards 2.5s;
  border-left: 87.5px solid transparent;
  border-right: 87.5px solid transparent;
  border-bottom: 150px solid #3b8070;
}

.Triangle--three {
  top: 60px;
  left: 35px;
  animation: goright 0.3s linear forwards 2.5s;
  border-left: 70px solid transparent;
  border-right: 70px solid transparent;
  border-bottom: 120px solid #35495e;
}

.Triangle--four {
  top: 120px;
  left: 70px;
  animation: godown 0.3s linear forwards 2s;
  border-left: 35px solid transparent;
  border-right: 35px solid transparent;
  border-bottom: 60px solid #fff;
}

/* orange */
.orange .Triangle--one {
  border-bottom: 180px solid #b87b41;
}

.orange .Triangle--two {
  border-bottom: 150px solid #80683b;
}

.orange .Triangle--three {
  border-bottom: 120px solid #5e4835;
}

/* pink */
.pink .Triangle--one {
  border-bottom: 180px solid #b441b8;
}

.pink .Triangle--two {
  border-bottom: 150px solid #753b80;
}

.pink .Triangle--three {
  border-bottom: 120px solid #59355e;
}

@keyframes turn {
  100% {
    transform: rotateX(0deg);
  }
}

@keyframes godown {
  100% {
    top: 180px;
  }
}

@keyframes goright {
  100% {
    left: 70px;
  }
}
</style>
