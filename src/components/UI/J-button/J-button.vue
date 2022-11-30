<template>
    <button
        class="j-button"
        :class="buttonClasses">
        {{ text }}
    </button>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';

@Options({
    computed: {
        buttonClasses() {
            return {
                'disabled': this.disabled,
            }
        }
    },
    props: {
        disabled: {
            type: Boolean,
            default: false,
        },
        text: {
            type: String,
            default: '',
        },

    }
})
export default class JButton extends Vue {}
</script>

<style lang="scss">
.j-button {

}
</style>
