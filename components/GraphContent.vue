<template>
  <section>
    <ChartAt :sections="array" />
  </section>
</template>

<script>
import ChartAt from '~/components/ChartAt/ChartAt'

export default {
  data() {
    return {
      array: [
        {
          title: 'REVENUE',
          money: 200000,
          section: [
            { label:'Tablet', value: 0, color: '#98d354', money: 120000 },
            { label:'Smartphone', value: 0, color: '#697b56', money: 80000 },
          ]
        },
        {
          title: 'IMPRESIONS',
          money: 50000,
          section: [
            { label:'Tablet', value: 0, color: '#7da9ba', money: 20000 },
            { label:'Smartphone', value: 0, color: '#9fc8d7', money: 30000 },
          ]
        },
        {
          title: 'VISITS',
          money: 600000,
          section: [
            { label:'Tablet', value: 0, color: '#e6c558', money: 480000 },
            { label:'Smartphone', value: 0, color: '#b87e5a', money: 120000 },
          ]
        }
      ]
    }
  },

  mounted() {
    this.getPercent()
  },

  methods: {
    getPercent() {
      var size = 0
      var money = 0
      var newValue = 0

      for(var count = 0; count < this.array.length; count++) {
        size = this.array[count].section.length
        money = parseInt(this.array[count].money)

        for(var array = 0; array < size; array++) {
          newValue = parseInt(this.array[count].section[array].money)
          this.array[count].section[array].value = this.percent(money, newValue)
        }
      }
      console.log(this.array)
    },

    percent(total, amount) {
      return (amount * 100) / total
    }
  },

  components: {
    ChartAt
  }
}
</script>
