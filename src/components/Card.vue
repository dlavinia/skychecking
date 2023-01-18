<template>
    <section class="parceiros">    
        <h2> {{ listItems.name }} </h2>
    </section>

</template>
<script>
export default {
  name: 'ParceirosListing',
  data() {
    return {
      listItems : Object
    }
  },
  methods: {

    async getData() {
      const res = await fetch("https://api.openweathermap.org/data/2.5/weather?q=Natal,BR&appid=465af90b1540b9ff8c6e6e5aa5fe175d&units=metric&lang=pt_br");
      const finalRes = await res.json();
      this.listItems = finalRes;
      console.log(finalRes)
    },

  },
  mounted() {
    this.getData()
  }
}

</script>
<style scoped>

</style>
