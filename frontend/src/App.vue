<template>
  <div
    v-if="isDrizzleInitialized"
    id="app">
    <header>
      <h1>Simple Drizzle DAPP</h1>
      Account:
      <drizzle-account units="Ether" precision="4"/>
    </header>

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

  }
</style>
