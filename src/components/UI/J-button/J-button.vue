<template>
    <button
        class="j-button btn"
        :class="buttonClasses"
        :disabled="isDisabled"
        :type="type"
        :loading="loading"
        v-bind="$attrs">
        <div class="j-button__loader" v-if="loading"></div>
        <slot>
            <div v-if="text">
                {{ text }}
            </div>
        </slot>
    </button>
</template>

<script setup lang="ts">
import {computed, defineProps} from "vue";

const buttonClasses = computed(() => {
    return [
        {
            'disabled': props.disabled,
            'loading': props.loading,
        }
    ]
})

const isDisabled = computed(() => {
    return props.disabled || props.loading;
})

const props = defineProps({
    disabled: {
        type: Boolean,
        default: false,
    },
    loading: {
        type: Boolean,
        default: true,
    },
    text: {
        type: String,
        default: '',
    },
    type: {
        type: String,
        default: 'button',
    }
});
</script>

<style lang="scss">
@import "@/style/index.scss";

.j-button {
    position: relative;
    width: auto;
    max-width: 100%;
    color: $white;
    background-color: $purple-medium;

    &.loading {
        & > * {
            opacity: 0;
        }
    }

    &__loader {
        content: "";
        position: absolute;
        bottom: 0;
        display: block;
        border-radius: 50%;
        width: 0;
        height: 0;
        margin: 8px;
        box-sizing: border-box;
        border: 10px solid #fff;
        border-color: #fff transparent #fff transparent;
        animation: hourglass 1.2s infinite;

        .j-button.loading & {
            opacity: 1;
        }
    }
}
</style>
