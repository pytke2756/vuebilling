<template>
  <div id="app">
    <table>
      <thead>
        <tr>
        <th>Termék</th>
        <th>Ár</th>
        <th>Mennyiség</th>
        <th>Operations</th>
        <th>Összérték</th>
      </tr>
      </thead>
      <tbody>
        <tr v-for="sor in rows"
            v-bind:key="sor.title">
            <td>{{sor.title}}</td>
            <td>{{sor.price}} Ft</td>
            <td>{{sor.quantity}}</td>
            <td>gombok</td>
            <td>{{sor.price * sor.quantity}} Ft</td>
        </tr>
        <tr>
          <td>
            <input type="text" placeholder="termék neve"> <!-- a   " v-model="uj.title" " elüntette a képet így kivettem-->
          </td>
          <td>
            <input type="number" placeholder="ár">
          </td>
          <td>
            <input type="number" placeholder="mennyiség">
          </td>
          <td>
            <button v-on:click="felvesz">Hozzáad</button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>

export default {
  name: 'App',
  components: {
    //Row,
  },
  data() {
    return {
      rows: [
        {
          title: 'Kerék',
          price: 100,
          quantity: 12
        },
        {
          title: 'Teleszkóp',
          price: 1000,
          quantity: 300
        },
        {
          title: 'Kormány',
          price: 230,
          quantity: 5
        },
        {
          title: 'Ajtó',
          price: 45120,
          quantity: 321
        },
      ]
    }
  },
  adatok:{
    uj:{
      title:"",
      price:"",
      quantity: "",
    },
  },
  methods:{
    felvesz(){
       this.rows.push({...this.adatok})
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
