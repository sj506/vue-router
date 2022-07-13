<template>
  <tr>
    <td>
      {{ pro.product_name }}
    </td>
    <td>{{ getPrice }}</td>
    <td>
      {{ pro.category }}
    </td>
    <td>{{ getDeliveryPrice }}</td>
    <DataBinding></DataBinding>
  </tr>
</template>
<script>
import DataBinding from '../views/DataBindingList.vue';

export default {
  components: { DataBinding },
  props: {
    pro: Object,
  },
  computed: {
    getPrice() {
      return this.numberComma(this.pro.price);
    },
    getDeliveryPrice() {
      return this.numberComma(this.pro.delivery_price);
    },
  },
  name: 'ProductItem',
  components: {},
  data() {
    return {
      sampleData: '',
    };
  },
  setup() {},
  created() {},
  mounted() {},
  unmounted() {},
  methods: {
    numberComma(num) {
      return String(num).replace(/\B(?=(\d{3})+(?!\d))/g, ',');
    },
  },
};
</script>
