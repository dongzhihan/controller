<template>
  <div>
    <div class="carGroup">
 
      <x-button v-for="item in list " class="car" @click.native="goTo(item.key)" :key="item.key" type="primary">{{item.value}}</x-button>
    </div>
  </div>
</template>
<style scoped>
  .carGroup {
    display: flex;
    flex-wrap: wrap;
  }

  .car {
    width: 100px;

    margin-top: 15px;
  }

</style>
<script>
  import {
    Selector,
    Group,
    XButton
  } from 'vux';
  import api from '../js/api';

  export default {
    data() {
      return {
        defaultValue: '',
        list: [{
          key: '1',
          value: '小车1'
        }, {
          key: '2',
          value: '小车2'
        }, {
          key: '3',
          value: '小车3'
        }, {
          key: '4',
          value: '小车4'
        }, {
          key: '5',
          value: '小车5'
        }, {
          key: '6',
          value: '小车6'
        }]
      };
    },
    components: {
      Selector,
      Group,
      XButton
    },
    methods: {
      goTo(carId) {


        //  this.$http.post(api.xxx, data, api.config).then((data) => {
        // if (data.data.Errcode === 0) {
        this.$router.push({
          name: 'carCtl',
          params: {
            id: carId
          }
        });
        // }
        // });
      }
    }
  };

</script>
