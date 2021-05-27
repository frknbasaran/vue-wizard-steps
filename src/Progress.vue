<template>
  <div class="progress">
    <div class="bar" :style="{ 'background-color': bgColor }">
      <div 
        :key="index" 
        v-for="index in sections.fillCount" 
        :style="{ 'background-color': fillColor, width: (100 / sections.titles.length) + '%' }"
        class="fill">
      </div>
    </div>
    <div class="label">
      <div 
        :key="title"
        v-for="title in sections.titles"
        :style="{ width: (100 / sections.titles.length) + '%' }"
        class="section">
        {{ title }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    sections: Object,
    bgColor: String,
    fillColor: String
  }
}
</script>

<style>
.progress {
  width: 100%;
}

.progress .section {
  height: 20px;
  text-align: center;
}

.progress .bar {
  display: flex;
  background-color: #E4F5B8;
  width: 100%;
  height: 20px;
  border-radius: 3px;
}

.progress .bar .fill:first-of-type {
  border-bottom-left-radius: 3px;
  border-top-left-radius: 3px;
}

.progress .bar .fill {
  background-color: #1F01B9;
}

.progress .bar .fill:last-of-type {
  border-top-right-radius: 3px;
  border-bottom-right-radius: 3px;
}

.progress .label {
  display: flex;
  width: 100%;
  height: 20px;
  font-weight: bold;
  margin-top: 10px;
}
</style>