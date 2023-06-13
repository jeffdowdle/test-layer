<script setup lang="ts">
import { useTideSite } from '#imports'

const site = await useTideSite()
</script>

<script lang="ts">
export default {
  name: 'TideWrapper'
}
</script>

<template>
  <TideBaseLayout
    :site="site"
    :page="{}"
    pageTitle="My cool page"
    pageLanguage="en-AU"
  >
    <template #aboveBody="{ hasBreadcrumbs }">
      <RplHeroHeader
        title="My cool page"
        :behind-nav="true"
        :breadcrumbs="hasBreadcrumbs"
      />
    </template>
    <template #body>
      <RplSitemap :items="site.menus.menuMain" />
    </template>
    <template #sidebar>
      <RplButton>Wow!</RplButton>
    </template>
  </TideBaseLayout>
</template>
