<template>
<div class="meh">
<constellation-cell v-for="(c, i) in cells" :key="i" />
</div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import ConstellationCell from './ConstellationCell.vue';

@Component({
    components: { ConstellationCell }
})
export default class Constellation extends Vue {
    private cells: string[] = [];

    private mounted() {
        for (let i = 0; i < 256; i++) {
            this.cells.push('meh');
        }
    }
}
</script>

<style lang="scss" scoped>
.meh {
    display: inline-grid;
    grid-template-columns: auto auto auto auto auto auto auto auto auto auto auto auto auto auto auto auto;
}
</style>
