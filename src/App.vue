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
      <section>
        <plans-tile></plans-tile>
      </section>
      <text-section v-for="text in infoTexts" :textData="text" :key="text.title">
      </text-section>
    </main>
  </div>
</template>

<script>
import PlansTile from './components/PlansTile'
import TextSection from './components/TextSection'

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
</style>
