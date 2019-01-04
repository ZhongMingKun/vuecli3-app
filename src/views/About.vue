<template>
  <div class="about">
    <h1>This is an about page</h1>
    <input type="text" v-model="getMsg">
    {{getMsg}}
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

  private defaultMsg: string = 'test';
  private msg: string = '';
  constructor() {
    super();
  }

  get getMsg() {
    return this.msg || this.defaultMsg;
  }

  set getMsg(val: string) {
    this.msg = val;
  }
}
</script>
