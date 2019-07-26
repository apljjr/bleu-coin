<template>
  <div class="container">
    <div>
      <p class="fontLineOne">{{textLineOne}}</p>
    </div>
    <div>
      <p>{{textLineTwo}}</p>
      <p><span class="boxSpan">{{textLineThreePartOne}}</span>{{textLineThreePartTwo}}</p>
    </div>
    <div class="paddingTop">
      <converter/>
    </div>
  </div>
</template>

<script>

import Converter from './Converter.vue'

export default {
  name: 'Container',
  components: {
    Converter
  },
  data() {
    return {
      textLineOne: `USD Best Price in Brazil`,
      textLineTwo: 
        `Compare and find in realtime the best 
        effective prices in Brazil's top USD exchanges, 
        considering fees.`,
      textLineThreePartOne: `Click on the exchange row`,
      textLineThreePartTwo: `to view operation details.`
    }
  }
}
</script>

<style scoped>
  .container {
    padding-top: 50px
  }
  .fontLineOne {
    font-size: 30px;
    color: black;
    padding-bottom: 25px;
  }
  .paddingTop {
    padding-top: 50px
  }

  .boxSpan {
    border: 1px solid #c7c7c7;
    background-color: #edf2f5;
    padding: 5px;
    margin-right: 5px;
    border-radius: 5px;
  }
  
</style>
