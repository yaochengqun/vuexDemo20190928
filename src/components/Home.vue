<template>
  <div class="home">
    {{$store.state.count}}
    <br>
    <input type="button" value="+" @click="handleAdd(1)">
    <input type="button" value="-" @click="handleReduce(1)">
    <br>
    {{c}}--{{gc}}
  </div>
</template>

<script>
import {mapActions,mapMutations,mapState,mapGetters} from 'vuex'
export default {
  methods:{
    ...mapActions({
      handleAdd:'actionsAddCount',
      handleReduce:'actionsReduceCount'
    }),
    ...mapMutations({
      mutaionsAdd:'mutationsAddCount',
      mutaionsReduce:'mutationsReduceCount',
    })
  },
  computed:{
    ...mapState({
      c:'count'
    }),
    ...mapGetters({
      gc:'gettersCount'
    })
  }
}
</script>

<style>

</style>