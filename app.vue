<!-- SPDX-FileCopyrightText: Copyright (c) 2022-2025 trobonox <hello@trobo.dev> -->
<!-- -->
<!-- SPDX-License-Identifier: CC0-1.0 -->

<template>
  <div>
    <NuxtLayout>
      <NuxtPage />
    </NuxtLayout>
  </div>
</template>

<script setup>
import { show } from "@tauri-apps/api/app";
import {
  attachConsole,
  trace,
  debug,
  info,
  warn,
  error,
} from "@tauri-apps/plugin-log";

onMounted(async () => {
  setTimeout(() => {
    show();
  }, 50);

  await attachConsole();

  console.trace = trace;
  console.log = debug;
  console.info = info;
  console.warn = warn;
  console.error = error;
});
</script>
