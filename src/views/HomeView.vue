<script setup lang="ts">
import type { HeaderDeploymentsItem } from '@killbill/vue-aviate-components';
import * as aviate from '@killbill/aviate-client-js';
import axios from 'axios';
import {onMounted, ref} from "vue";

function createDeploymentItem(): HeaderDeploymentsItem {
  return {
    user_name: 'dummy',
    password: 'dummy'
  };
}

const aviateConfig = new aviate.Configuration({
  username: 'admin',
  password: 'password',
  basePath: 'http://localhost:8080/plugins/aviate-plugin',
  apiKey: aviate.apiKey('bob', 'lazar')
});

const result = ref<aviate.Quote[]>([]);

onMounted(async () => {
  const quoteApi = new aviate.QuoteApi(aviateConfig, undefined, axios);
  const response = await quoteApi.getAllQuotes(undefined);
  result.value = response.data;
});
</script>

<template>
  <main>
    <div>{{ createDeploymentItem() }}</div>
    <div>{{ result }}</div>
  </main>
</template>