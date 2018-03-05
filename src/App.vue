<template>
  <div id="app">
    <main>
      <header class="header">
        <div class="header__title-container">
          <img class="header__title-container__logo" src="./assets/logo-square.svg"/>
          <h1 class="header__title-container__text">{{title}}</h1>
        </div>
        <i class="header__subtitle">{{subtitle}}</i>
      </header>
      <section class="demo-section">
        <b class="demo-section__text">Check out our demo <a href="#" @click="goToDemo">here!</a></b>
      </section>
        <plans-tile></plans-tile>
      </section>
      <text-section v-for="text in infoTexts" :textData="text" :key="text.title">
      </text-section>
    </main>
  </div>
</template>

<script>
import PlansTile from './components/AppPlansTile'
import TextSection from './components/AppTextSection'

export default {
  name: 'app',
  components: {
    PlansTile,
    TextSection
  },
  data () {
    return {
      title: 'Beerboard',
      subtitle: 'A simple reliable sollution to your beer managment',
      infoTexts: [{
        title: 'What even is this?',
        text: 'Blah blah cool intro more text ladadahdidah Blah blah cool intro more text ladadahdidah Blah blah cool intro more text ladadahdidah Blah blah cool intro more text ladadahdidah Blah blah cool intro more text ladadahdidah Blah blah cool intro more text ladadahdidah'
      }]
    }
  },
  methods: {
    goToDemo () {
      window.location = "https://bierbord.nl"
    }
  }
}
</script>
<!--TODO: add Roboto web font-->
<style>
body {
  margin: 0;
}

#app {
  font-family: 'Roboto', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

main {
  display: flex;
  align-content: center;
  align-items: center;
  flex-flow: column;
  text-align: center;
  margin-top: 30px;
  padding: 20px;
}

main > * {
  margin: 20px 0px;
}

.header {
  margin: 20px;
}

.header__title-container {
  display: flex;
}

.header__title-container__logo {
  margin: 5px;
}

.header__title-container__text {
  font-size: 68px;
  margin: 0px;
}

.header__subtitle {
  opacity: 0.71;
}

.demo-section {
  margin: 0px;
}

.demo-section__text a{
  /* remove the default underline */
  text-decoration: none;
  /* so the after pseudo can be positioned */
  position: relative;
  /* no blue/purple link color */
  color: inherit;
}

.demo-section__text a::after{
  content: "";
  position: absolute;
  bottom: 0px;
  left: 0;
  height: 2px;
  width: 100%;
  background: linear-gradient(-124deg, #EE1D1D 0%, #E38222 100%);
}

.demo-section__text a:active::after{
  content: "";
  position: absolute;
  bottom: 0px;
  left: 0;
  height: 2px;
  width: 100%;
  background: linear-gradient(-124deg, #fff 0%, #E38222 100%);
}
</style>
