<template>
    <section class="inline-block mr-4">
        <button>
            <svg xmlns="http://www.w3.org/2000/svg" height="80" viewBox="40 40 220 120">
                <circle cx="100" cy="100" r="60" fill="var(--color-accent)" />
                <circle cx="150" cy="100" r="60" fill="var(--color-secondary)" />
                <circle cx="200" cy="100" r="60" fill="var(--color-primary)" />
            </svg>

        </button>
    </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { useI18n } from 'vue-i18n';

export default defineComponent({
    setup() {
        const { t } = useI18n();
        return { t };
    },
});
</script>

<style scoped></style>