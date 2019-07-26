<template>
  <div class="row justify-content-center">
    <div class="inputFirst">
      <div class="input-group ">
        <money class="form-control textRight radius" 
          v-model="priceBRL" 
          v-bind="money"
          @keyup.native="changePrice(coinBRL)">
        </money>
        <div class="input-group-append ">
            <span class="input-group-text fundoMoeda radius">{{coinBRL}}</span>
        </div>
      </div>
    </div>
    <div class="inputSecond">
      <div class="input-group ">
        <money class="form-control textRight radius" 
          v-model="priceUSD" 
          v-bind="money"
          @keyup.native="changePrice(coinUSD)">
        </money>
        <div class="input-group-append ">
            <span class="input-group-text fundoMoeda radius">{{coinUSD}}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { Money } from 'v-money'
import Axios from 'axios'

export default {
  name: 'Conversor',
  components: {
    Money
  },
  data() {
    return {
      coinBRL: 'BRL',
      coinUSD: 'USD',
      priceBRL: 0.00,
      priceUSD: 0.00,
      money: {
        priceComponent: null,
        decimal: ',',
        thousands: '.',
        precision: 2,
        masked: false
      }
    }
  },
  methods: {
    changePrice(coin) {
      Axios.get('https://economia.awesomeapi.com.br/all/USD-BRL').then((res) => {
        let dollar = Number(res.data.USD.bid.replace(",", "."))
        if(coin === 'BRL') {
          this.priceUSD = this.priceBRL / dollar
        } 
        if(coin === 'USD') {
          this.priceBRL = this.priceUSD * dollar
        }
      })
    }
  }
}
</script>

<style scoped>
  .container {
    padding-top: 50px
  }

  .tamnhoFont {
    font-size: 25px
  }

  .inputFirst {
    max-width: 170px;
    padding-right: 5px 
  }
  .inputSecond {
    max-width: 170px;
    padding-left: 5px 
  }
  .fundoMoeda {
    background-color: white;
    font-weight: bold;
  }

  .form-control:focus {
    border-color: none;
    -webkit-box-shadow: none;
    box-shadow: none;
  }

  .textRight {
    text-align: right;
  }

  .radius {
    border-radius: 0.5rem;
  }
</style>
