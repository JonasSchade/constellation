<template>
    <canvas ref="canvas" width="30" height="30"></canvas>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

const WIDTH = 30;
const HEIGHT = 30;

@Component
export default class ConstellationCell extends Vue {
    private interval?: number;

    private mounted() {

        const ctx = (this.$refs.canvas as HTMLCanvasElement).getContext('2d');

        if (!ctx) return;

        ctx.fillStyle = '#FF0000';
        ctx.strokeRect(0, 0, 30, 30);

        this.interval = setInterval(this.onInterval, 500);

    }

    private onInterval() {
        const canvas = this.$refs.canvas as HTMLCanvasElement;

        if (!canvas) return;

        const ctx = canvas.getContext('2d');

        if (!ctx) return;

        ctx.fillStyle = '#00FF00';

        const genRandomNumber = () => {
            const num = Math.random() * 10;

            return Math.random() > 0.5 ? num * -1 : num;
        };

        const xRand: number = genRandomNumber();
        const yRand: number = genRandomNumber();

        ctx.fillRect(15 + xRand, 15 + yRand, 2, 2);
    }
}
</script>