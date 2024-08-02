<template>
    <div class="edge-opacity"
        :style="`--top: ${_range[0]}; --right: ${_range[1]}; --bottom: ${_range[2]}; --left: ${_range[3]}; --edge-opacity: ${_edgeOpacity};`">
        <div class="opacity-left-right">
            <div class="opacity-top-bottom">
                <slot></slot>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "EdgeOpacity",
    props: {
        range: {
            type: String,
            default: '5%',
        },
        edgeOpacity: {
            type: Number,
            default: 0,
        },
    },
    computed: {
        _range() {
            if (!this.range) {
                this.range = '5%';
            }
            let arr = this.range.split(' ');
            if (arr.length === 1) {
                return [arr[0], arr[0], arr[0], arr[0]];
            } else if (arr.length === 2) {
                return [arr[0], arr[1], arr[0], arr[1]];
            } else if (arr.length === 3) {
                return [arr[0], arr[1], arr[2], arr[1]];
            } else if (arr.length >= 4) {
                return [arr[0], arr[1], arr[2], arr[3]];
            }
        },
        _edgeOpacity() {
            return this.edgeOpacity * 100 + '%';
        }
    }
}
</script>

<style scoped>
.edge-opacity .opacity-left-right {
    height: 100%;
    /* 遮罩，为了左右边缘透明效果 */
    mask: linear-gradient(to right,
            rgba(255, 255, 255, var(--edge-opacity)) 0%,
            white var(--left),
            white calc(100% - var(--right)),
            rgba(255, 255, 255, var(--edge-opacity)) 100%) no-repeat center/100% 100%;

}

.edge-opacity .opacity-top-bottom {
    height: 100%;
    /* /遮罩，为了上下边缘透明效果 */
    mask: linear-gradient(to bottom,
            rgba(255, 255, 255, var(--edge-opacity)) 0%,
            white var(--top),
            white calc(100% - var(--bottom)),
            rgba(255, 255, 255, var(--edge-opacity)) 100%) no-repeat center/100% 100%;
}
</style>