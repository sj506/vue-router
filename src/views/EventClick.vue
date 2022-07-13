<template>
  <div>
    <div>
      <h1>EventClick</h1>
      <button @click="increaseCnt(), printConsole()">Add 1</button>
      <p>The counter is : {{ cnt }}</p>
    </div>
    <div>
      <select v-model="selectedValue" @change="changSelect">
        <option>서울</option>
        <option>부산</option>
        <option>제주</option>
        <!-- Value 는 자동으로 option 안에 text 가 됨 -->
      </select>
    </div>
    <div>
      <input type="text" @keyup="ChangeTxtVal()" @keyup.enter="enterTxtVal()" v-model="txtVal" />
    </div>
  </div>
</template>
<script>
export default {
  name: '',
  components: {},
  data() {
    return {
      cnt: 0,
      selectedValue: '',
      txtVal: '',
    };
  },
  setup() {},
  created() {},
  mounted() {},
  unmounted() {},
  methods: {
    increaseCnt() {
      return this.cnt++;
    },
    ChangeTxtVal() {
      console.log(this.txtVal);
    },
    enterTxtVal() {
      console.log(this.txtVal);
      this.txtVal = '';
    },
    printConsole() {
      console.log(this.cnt);
    },
    changSelect() {},
  },
};
</script>
