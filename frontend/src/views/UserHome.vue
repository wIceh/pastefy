<script setup lang="ts">
import PasteList from '@/components/lists/PasteList.vue'
import FolderList from '@/components/lists/FolderList.vue'
import { useTitle } from '@vueuse/core'
useTitle(`Home | IcePaste`)
</script>

<template>
  <div class="flex flex-col gap-14">
    <div>
      <h2 class="mb-4 text-2xl font-bold">Folders</h2>

      <FolderList route="/api/v2/user/folders" />
    </div>

    <div>
      <h2 class="mb-4 text-2xl font-bold">Pastes</h2>

      <PasteList route="/api/v2/user/pastes" :params="{ page_limit: 8, hide_children: 'true' }" />
    </div>
  </div>
</template>
