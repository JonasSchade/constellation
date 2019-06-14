<template>
  <Constellation />
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import Constellation from './components/Constellation.vue';

@Component({
    components: { Constellation }
})
export default class App extends Vue {}
</script>

