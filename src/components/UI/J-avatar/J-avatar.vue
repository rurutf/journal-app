<template>
    <div
        class="j-avatar"
        @click="clickHandler">
        <span class="j-avatar__text">
            {{ initialsName }}
        </span>
    </div>
</template>

<script lang="ts">
import {defineComponent} from "vue";

export default defineComponent({
    computed: {
        initialsName(): string {
            const fullNameArray: string[] = this.initialsName.split(' ');
            const firstCharsets = fullNameArray.map(item => item[0]).filter(i => i);

            return firstCharsets.slice(0, 2).join('');
        }
    },
    methods: {
        clickHandler(): void {
            this.$emit('click');
        }
    },
    props: {
        initialsName: {
            type: String,
            default: '',
        }
    }
})
</script>

<style lang="scss">
@import "@/style/index.scss";

.j-avatar {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 42px;
    height: 42px;
    overflow: hidden;
    background-clip: padding-box;
    border-radius: 50%;
    background: $gradient-pale-pink;

    &__text {

    }
}
</style>
