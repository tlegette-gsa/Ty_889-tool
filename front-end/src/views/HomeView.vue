<script setup>
import { onMounted } from "vue";
import { useSearchStore } from "@/stores/search";

import SearchInput from "../components/SearchInput.vue";
import GSAHeader from "../components/GSAHeader.vue";

// reset input when coming back to homepage
const store = useSearchStore();
onMounted(() => {
  store.resetState();
});
</script>

<template>
  <div class="background flex-fill">
    <GSAHeader :link-home="false" />
    <div
      id="main-container"
      class="wide-layout"
    >
      <main id="main-content">
        <div class="grid-container">
          <div class="padding-top-8">
            <h2 class="font-sans-lg margin-bottom-1">
              Check to see if an entity has a section 889 representation in
              SAM.gov
            </h2>

            <p class="margin-top-0">
              Search by business name, website, CAGE code, or SAM.gov Unique
              Entity ID (UEI)
            </p>

            <SearchInput />
          </div>
          <div class="padding-bottom-10">
            <p>
              This search only checks for Section 889 representations in an
              entity’s SAM.gov record. Only entities doing business above the
              Micro-Purchase Threshold (MPT) are required to register in
              SAM.gov. Contracts classified as For Official Use Only (FOUO) or contractors who do not wish for their information to be publicly available will not appear in search results.
            </p>

            <p>
              <b>Please Note:</b> If an entity representation is not available,
              cardholders may still be permitted to purchase from a listed
              entity. However, the cardholder would be responsible for
              documenting compliance with Section 889 in accordance with any
              applicable agency requirements.
            </p>
          </div>
        </div>
      </main>
    </div>
  </div>
</template>
