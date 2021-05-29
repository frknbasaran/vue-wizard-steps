![vuegrass-bar gif](https://github.com/frknbasaran/vuegress-bar/blob/master/docs/vuegress-bar.gif?raw=true)

# vue-wizard-steps

> Lightweight and customizable step-by-step progress/wizard component for Vue.

### Step 1: Installation

    yarn add vue-wizard-steps

### Step 2: Add to project

    import  Vue  from  'vue';
    import  VuegressBar  from  'vuegress-bar';
    import  App  from  './App.vue';
    
    Vue.component("vuegress-bar", VuegressBar);
    
    new  Vue({
	    render: h => h(App),
    }).$mount('#app');

### Step 3: Use component in view

    <template>
    	<vuegress-bar :sections="sections" :bgColor="bgColor" :fillColor="fillColor" />
    </template>
    
    <script>
    export default {
    data() {
    	return {
    		sections: {
    			titles:  ['summary',  'shipping',  'payment',  'checkout'],
    			fillCount: 2
    		},
    		bgColor: '#E4F5B8',
    		fillColor: '#1F01B9'
    	};
    }
    }
    </script>

That's all.

### Props

|Prop name| Type  | Description | Required |
|--|--|--|--|
|sections|Object|Object that contains progress bar settings| yes
|sections.titles| Array | String array that represents step titles | yes 
|sections.fillCount| Number | Filled step count | yes
|bgColor| String | Background color of progress bar as hexadecimal | no
|fillColor| String | Color of filled bars on progress as hexadecimal | no
