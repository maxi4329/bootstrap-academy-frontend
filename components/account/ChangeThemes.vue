<template>
    <article class="bg-secondary card style-card flex flex-col items-center justify-center">
        <PaintBrushIcon class="h-10 w-10 text-accent mb-4 max-w-xl" />

        <h2 class="text-heading-2">
            {{ t("Headings.Themes") }}
        </h2>

        <div class="flex items-center space-x-4 mt-2 mb-8">
            <CheckCircleIcon class="h-8 w-8 text-accent max-w-xl" />

            <div class="flex flex-col items-center">
                <p class="text-center">
                    {{ t("Body.AdjustTheDesign") }}
                </p>
            </div>
        </div>

        <NuxtLink to="/account/themes">
            <Btn>{{ t('Buttons.OpenThemeSettings') }}</Btn>
        </NuxtLink>
    </article>
</template>

<script lang="ts">
import { CheckCircleIcon, ShieldExclamationIcon } from '@heroicons/vue/24/outline';
import { PaintBrushIcon } from '@heroicons/vue/24/solid';
import { defineComponent } from 'vue';
import { useI18n } from 'vue-i18n';

export default defineComponent({
    components: {
        CheckCircleIcon,
        ShieldExclamationIcon,
        PaintBrushIcon
    },
    setup() {
        const { t } = useI18n();

        return { t };
    },
});
</script>

<style scoped></style>