<template>
  <div v-if="isDrizzleInitialized" id="app">
    <section>
      <h2>Show Accounts</h2>
      <drizzle-account units="Ether" precision="4"/>

    </section>
    <section>
      <h2>Simple Storage</h2>
      <drizzle-contract
        contract-name="SimpleStorage"
        method="storedData"
        label="Value"/>

      <drizzle-contract-form
        contract-name="SimpleStorage"
        method="set"
        :placeholders="['Value']"/>

    </section>
  </div>
  <div v-else>
    Loading
  </div>
</template>

<script>
  import { mapGetters } from 'vuex'

  export default {
    name: 'app',
    computed: mapGetters('drizzle', ['isDrizzleInitialized']),
  }
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
