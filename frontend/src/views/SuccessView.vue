<script setup>
import AppPopup from "@/common/components/popup/AppPopup.vue";
import AppPopupTitle from "@/common/components/popup/AppPopupTitle.vue";
import AppPopupButton from "@/common/components/popup/AppPopupButton.vue";
import { computed } from "vue";
import { useAuthStore } from "@/stores/auth";

const authStore = useAuthStore();

const redirectRouteName = computed(() =>
  authStore.isAuthenticated ? "orders" : "home"
);
</script>

<template>
  <AppPopup>
    <RouterLink :to="{ name: redirectRouteName }" class="close">
      <span class="visually-hidden">Закрыть попап</span>
    </RouterLink>
    <AppPopupTitle> Спасибо за заказ </AppPopupTitle>
    <p>Мы начали готовить Ваш заказ, скоро привезём его вам ;)</p>
    <AppPopupButton>
      <RouterLink :to="{ name: redirectRouteName }" class="button">
        Отлично, я жду!
      </RouterLink>
    </AppPopupButton>
  </AppPopup>
</template>
