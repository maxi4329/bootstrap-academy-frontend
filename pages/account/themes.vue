<!--
❌ Responsive UI
❌ Page Title
❌ Translation
❌ Animation
❌ middleware

❌ Tested on chrome
❌ Tested on firefox
❌ Tested on safari
❌ Tested on android mobile
❌ Tested on apple mobile

❌ Api implemented
❌ Form Submission Process
❌ Form Post Api Error Handling + ❌ Translation
❌ Form Post Api Success Handling + ❌ Translation
-->

<template>
  <section class="container-fluid pt-container pb-container h-screen-inner min grid place-items-center">
    <Transition mode="out-in" name="slide-up-down">
      <section class="container-form">
        <SectionTitle heading="Headings.Themes" />
        <ThemeSelector class="defaultTheme" onclick="document.documentElement.setAttribute('data-theme', '')" />
        <ThemeSelector class="accessibilityTheme"
          onclick="document.documentElement.setAttribute('data-theme', 'accessibility')" />
        <InputRange :min="0" :max="100" :modelValue="50" :label="t('Headings.FontSize')" suffix="px" :reduce="0" />
        <InputColor :label="t('Headings.BackgroundColor')" />
        <InputColor :label="t('Headings.TextColor')" />
      </section>
    </Transition>
  </section>
</template>

<script lang="ts">
import { useI18n } from 'vue-i18n';

definePageMeta({
  layout: 'inner',
  middleware: ['auth'],
});

export default {
  head: {
    title: 'Cofigure themes',
  },
  setup() {
    const { t } = useI18n();
    const form: any = reactive({
      salary_min: {
        min: 0,
        max: 10000,
        value: "props.filters?.salary_min ?? 0",
      }
    })
    const router = useRouter();
    const dialog = <any>reactive({});
    onMounted(async () => {
      Object.assign(dialog, {
        primaryBtn: {
          label: "Headings.Themes",
          onclick: () => {
            router.push("/account");
          },
        },
        secondaryBtn: null,
      });
    });

    const config = useRuntimeConfig().public;
    const accountLink = computed(() => {

      return `${config.BASE_WEB_URL}/account`;
    });

    return { t, accountLink };
  },
};
</script>

<style scoped></style>