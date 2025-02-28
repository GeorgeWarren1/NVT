<script setup lang="ts">
import type { HTMLAttributes } from 'vue';
import { computed } from 'vue';
import { useAppearance } from '@/composables/useAppearance';

defineOptions({
    inheritAttrs: false,
});

interface Props {
    className?: HTMLAttributes['class'];
}

defineProps<Props>();

const { appearance } = useAppearance();

const logoSrc = computed(() => {
    if (appearance.value === 'dark') {
        return '/NVT LOGO B.png';
    }
    return '/NVT LOGO W.png';
});
</script>

<template>
    <img
        :src="logoSrc"
        :class="[className, 'size-12 md:size-8']"
        v-bind="$attrs"
        alt="Logo"
    />
</template>
