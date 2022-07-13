<template>
  <div>
    <div>
      <h1>나의 이름은 홍길동입니다.</h1>
      <input type="number" v-model.number="numberModel" />
      {{ numberModel + numberModel }}
      {{ printNumber }}
    </div>
    <div>
      <label>여성<input type="radio" v-model.number="gender" value="0" /></label>
      <label>남성<input type="radio" v-model.number="gender" value="1" /></label>
      {{ printGender }}
    </div>
    <div v-html="htmlString"></div>
    <div>{{ htmlString }}</div>
    <hr />
    <div>
      <textarea v-model="message"></textarea>
    </div>
    <div>
      <select>
        <option :value="city.code" v-for="city in cityList" :key="city.code">{{ city.title }}</option>
      </select>
    </div>
    <div>
      <label><input type="checkbox" v-model="basketball" />농구</label>
      {{ basketball }}
      <label><input type="checkbox" v-model="football" true-value="1" false-value="0" />풋볼</label>
      {{ football }}
    </div>
    <div>
      <input type="text" v-model="textValue" />
      <input type="text" v-model="textValue2" />
      <button type="button" v-bind:disabled="textValue == '' || textValue !== textValue2">전송</button>
      <p v-bind:hidden="textValue == '' || textValue === textValue2" style="color: red">비밀번호가 일치하지 않습니다</p>
    </div>
    <hr />
    <div>
      <div class="container" v-bind:class="{ active: isActive, 'text-red': hasError }">Class Binding</div>
      <label>active<input type="checkbox" v-model="isActive" /></label>
      <label>text-red<input type="checkbox" v-model="hasError" /></label>
    </div>
    <hr />
    <div>
      <div class="container" :class="claArr">Class Binding</div>
    </div>
    <hr />
    <div>
      <div :style="styleObj">인라인 스타일 바인딩</div>
    </div>
  </div>
</template>
<style>
.container {
  width: 100%;
  height: 200px;
}
.active {
  background-color: yellow;
}
.text-red {
  color: red;
  font-weight: bold;
}
</style>
<script>
export default {
  name: '',
  components: {},
  data() {
    return {
      styleObj: {
        color: 'red',
        fontSize: '30px',
      },
      claArr: ['active', 'text-red'],
      activeClass: 'active',
      errorClass: 'text-red',
      isActive: true,
      hasError: false,
      numberModel: 3,
      gender: 0,
      htmlString: '<p style="color: red">This is a red string</p>',
      message: 'textarea입니다',
      cityList: [
        { title: '대구', code: '053' },
        { title: '서울', code: '02' },
        { title: '부산', code: '056' },
      ],
      basketball: true,
      football: '0',
      textValue: '',
      textValue2: '',
    };
  },
  computed: {
    // computed = 바뀌면 뭘로 찍겠다!
    // watch = 바뀌면 뭐 할래?
    printNumber() {
      return this.numberModel + 3;
    },

    printGender() {
      return this.gender == 0 ? '남성' : '여성';
    },
  },
  setup() {},
  created() {},
  mounted() {},
  unmounted() {},
  methods: {},
};
</script>
