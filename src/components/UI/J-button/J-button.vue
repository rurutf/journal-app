<template>
    <button
        class="j-button btn"
        :class="buttonClasses"
        :disabled="isDisabled"
        :type="type"
        v-bind="$attrs">
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
                'loading': this.loading,
            }
        },
        isDisabled() {
            return this.disabled || this.loading;
        }
    },
    props: {
        disabled: {
            type: Boolean,
            default: false,
        },
        loading: {
            type: Boolean,
            default: false,
        },
        text: {
            type: String,
            default: '',
        },
        type: {
            type: String,
            default: 'button',
        }
    }
})
export default class JButton extends Vue {}
</script>

<style lang="scss">
.j-button {

}
</style>
