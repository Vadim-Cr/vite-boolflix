<script >
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import { store } from './store';

export default {
  components: {
    AppHeader,
    AppMain,
  },
  data() {
    return {
      store,
    }
  },
}

</script>

<template>
  <AppHeader message="BOOLFIX" />
  <AppMain />
</template>

<style lang="scss">
@use "./components/style/general.scss";
</style>
