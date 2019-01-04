<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld :msg="msg" @msgChange="msg = $event"/>
    <button @click="clickHandler()">{{message}}</button>
    <button @click="msg = 'Welcome to Your Vue.js + TypeScript App'">resetMsg</button>
    {{testArr}}
  </div>
</template>

<script lang="ts">
import HelloWorld from '@/components/HelloWorld.vue';
import { Component, Vue, Watch } from 'vue-property-decorator';

@Component({
  components: {
    HelloWorld,
  },
})
export default class Home extends Vue {

  private msg: string = 'Welcome to Your Vue.js + TypeScript App';
  private message: number = 1;
  private testArr: any[] = [{test: 3}, {test: 4}];

  constructor() {
    super();
  }

  private clickHandler() {
    this.message++;
    this.testArr[0].test = this.message;
  }

  mounted() {
    console.log('lalalal');
  }

  @Watch('testArr', {deep: true, immediate: true})
  onMessageChange(val: number, old: number) {
    console.log('ssudas', val); return;
  }
}
</script>
