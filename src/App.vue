<template>
  <div id="app">
    <div class="intro"></div>
    <div class="wrapper">
      <img alt="Me" class="image" src="./assets/photo.jpg">
      <h1>Kibala Ivan</h1>
      <p>Web, Javascript, Vue, gRPC-Web</p>
      <div class="links-wrapper">
        <a target="_blank" href="http://github.com/kibala145/" class="image-32-link">
          <img src="./assets/github.png" alt="github logo">
        </a>
        <a target="_blank" href="mailto:kibala.dev@gmail.com" class="image-32-link">
          <img src="./assets/gmail.png" alt="gmail logo">
        </a>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'App'
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Exo+2:ital,wght@1,100&display=swap');

#app {
  font-family: 'Exo 2', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  overflow: auto;
  height: 100%;
}

html, body {
  height: 100%;
}

h1 {
  font-weight: normal;
}

body {
  background-color: #EEEEEE;
  margin: 0;
  animation-name: body-animation;
  animation-duration: 1.2s;
  animation-iteration-count: 1;
  animation-fill-mode: forwards;
  animation-timing-function: cubic-bezier(0.23, 1, 0.320, 1);
  animation-delay: .5s;
}

* {
  box-sizing: border-box;
}

.wrapper {
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  animation-name: wrapper-animation;
  animation-delay: 1.2s;
  animation-duration: 1s;
  animation-fill-mode: forwards;
  opacity: 0;
  filter: blur(5px);
  padding-top: 24px;
  padding-bottom: 24px;
  overflow: auto;
}

.intro {
  background-color: white;
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  animation-name: intro-animation;
  animation-duration: 1.2s;
  animation-iteration-count: 1;
  animation-fill-mode: both;
  animation-timing-function: cubic-bezier(0.23, 1, 0.320, 1);
  animation-delay: .5s;
}
.image {
  border-radius: 50%;
  width: 256px;
  height: 256px;
  margin-bottom: 12px;
  animation: image-animation 2s cubic-bezier(0.175, 0.885, 0.32, 1.275) 1.2s 1;
  animation-fill-mode: forwards;
  transform: scale(1.5);
  transition: filter .3s ease-in-out;
}
a.image-32-link {
  height: 32px;
  display: block;
  img {
    height: 100%;
  }
}
.links-wrapper {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: flex-start;
  margin-top: 12px;
  .image-32-link {
    opacity: 0;
    transform: translateX(10px);
    margin-left: 12px;
    &:first-child {
      margin-left: 0;
    }
    @for $i from 1 through 3 {
      &:nth-child(#{$i}) {
        animation-delay: 2s + (.3s*$i);
      }
    }
    animation-name: link-animation;
    animation-timing-function: cubic-bezier(0.25, 0.46, 0.45, 0.94);
    animation-duration: .3s;
    animation-fill-mode: forwards;
  }
}
@keyframes intro-animation {
  0% {
    clip-path: circle(100%);
  }
  50% {
    clip-path: circle(0);
  }
  100% {
    clip-path: circle(100%);
  }
}

@keyframes wrapper-animation {
  100% {
    opacity: 1;
    filter: blur(0);
  }
}

@keyframes body-animation {
  0% {
    background-color: #EEEEEE;
  }
  50% {
    background-color: #EEEEEE;
  }
  100% {
    background-color: #FF6F00;
  }
}
@keyframes link-animation {
  100% {
    opacity: 1;
    transform: none;
  }
}
@keyframes image-animation {
  100% {
    transform: none;
  }
}
</style>
