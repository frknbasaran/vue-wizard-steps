<template>
  <div id="app">
    <WizardSteps id="wizard" :sections="sections"/>
    <div v-if="sections.fillCount === 0" class="content">
      <h1>Contact Informations</h1>
      <div class="navigation-buttons">
        <button @click="sections.fillCount = 1">next</button>
      </div>
    </div>
    <div v-if="sections.fillCount === 1" class="content">
      <h1>Security Informations</h1>
      <div class="navigation-buttons">
        <button @click="sections.fillCount = 0">previous</button>
        <button @click="sections.fillCount = 2">next</button>
      </div>
    </div>
    <div v-if="sections.fillCount === 2" class="content">
      <h1>Profile Informations</h1>
      <div class="navigation-buttons">
        <button @click="sections.fillCount = 1">previous</button>
        <button @click="sections.fillCount = 3">finish</button>
      </div>
    </div>
    <div v-if="sections.fillCount === 3" class="content">
      <h1>Finished!</h1>
    </div>
  </div>
</template>

<script>
import WizardSteps from 'vue-wizard-steps';

export default {
  components: {
    WizardSteps
  },
  data() {
    return {
      sections: {
        // titles array for step
        titles:  ['contact', 'security', 'profile'],
        // filled step count as initially
        fillCount: 0
      },
      // optional background color 
      bgColor: '#E4F5B8',
      // optional filled step background color 
      fillColor: '#1F01B9'
    }
  }
}
</script>

<style>
#app {
  font-family: Helvetica, sans-serif;
  display: flex;
  flex-direction: column;
  align-items: center;
}
#wizard {
  width: 1024px;
}
.content {
  width: 1024px;
}
.navigation-buttons {
  display: flex;
  justify-content: space-between;
}
</style>