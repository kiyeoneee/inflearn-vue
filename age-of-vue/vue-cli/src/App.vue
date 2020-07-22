<template>
  <div>
  <!-- <app-header v-bind:프롭스 속성 이름="상위 컴포넌트의 데이터 이름"></app-header> -->
    <app-header v-bind:propsdata="str" v-on:renew="renewStr"></app-header>
  </div>
  <!-- <div id="app"> -->
    <!-- 파스칼 케이스 -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <!-- 케밥 케이스 -->
    <!-- <hello-world></hello-world> -->
  <!-- </div> -->
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import AppHeader from './components/AppHeader.vue';

export default {
  // 인스턴스 옵션 속성 or 컴포턴트 옵션 속성
  name: 'App',
  data: function() {
    return {
      str: 'Header'
    }
  },
  components: {
    'app-header': AppHeader
    // HelloWorld // == 'hello-world': HelloWorld
  },
  methods: {
    renewStr: function() {
        this.str = 'hi';
    }
  }
}
</script>

<style>
</style>
