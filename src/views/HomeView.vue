<script setup lang="ts">
import TheWelcome from '../components/TheWelcome.vue'
import type { HeaderDeploymentsItem } from 'vue-aviate-components';
import * as aviate from 'aviate-client-js';

function createDeploymentItem(): HeaderDeploymentsItem {
  return null;
}

function createQuoteApi(): aviate.QuoteApi {
  return null;
}
</script>

<template>
  <main>
    <TheWelcome />
  </main>
</template>