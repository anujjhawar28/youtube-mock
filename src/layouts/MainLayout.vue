<template>
  <q-layout view="hHh Lpr lff">
    <q-header class="bg-white">
      <q-toolbar
        style="margin-top: -10px"
        class="row justify-between items-center"
      >
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          color="grey-7"
          size="18px"
          @click="toggleLeftDrawer"
        />

        <div
          class="full-width row wrap justify-start items-center content-start q-pb-none col-12 col-sm-6 col-md-8"
        >
          <div class="col-2 hide-mobile">
            <img
              alt="Youtube Logo"
              src="~assets/youtube.jpg"
              width="100px"
              height="70px"
            />
          </div>

          <q-space />
          <div class="col-5">
            <q-input
              outlined
              v-model="searchQuery"
              dense
              placeholder="Search..."
              rounded
            >
              <template v-slot:append>
                <q-icon name="keyboard" class="q-mr-xs" />
                <q-btn
                  icon="search"
                  class="q-px-md"
                  @click="search"
                  round
                  dense
                />
              </template>
            </q-input>
          </div>
          <q-icon
            name="mic"
            color="grey-7"
            size="25px"
            class="q-ml-sm cursor-pointer"
          />
          <q-space />

          <div
            class="text-white rounded-borders row flex-center cursor-pointer"
          >
            <q-icon
              name="more_vert"
              class="vertical-dots"
              color="grey-7"
              size="25px"
            />
            <q-menu>
              <q-list>
                <q-item clickable v-close-popup>
                  <q-item-section>Option 1</q-item-section>
                </q-item>
                <q-item clickable v-close-popup>
                  <q-item-section>Option 2</q-item-section>
                </q-item>
                <q-item clickable v-close-popup>
                  <q-item-section>Option 3</q-item-section>
                </q-item>
              </q-list>
            </q-menu>
          </div>

          <div>
            <q-btn outline rounded color="primary">
              <div>
                <q-icon name="account_circle" />
                <span>Profile</span>
              </div>
            </q-btn>
          </div>

          <q-icon
            name="invert_colors"
            inverted
            color="grey-7"
            size="25px"
            class="q-ml-sm cursor-pointer"
          />
        </div>
      </q-toolbar>
    </q-header>

    <q-drawer v-model="leftDrawerOpen" show-if-above side="left">
      <q-list>
        <EssentialLink
          v-for="link in linksList"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup>
import { ref } from "vue";
import EssentialLink from "components/EssentialLink.vue";

defineOptions({
  name: "MainLayout",
});

const linksList = [
  {
    title: "Home",
    icon: "home",
  },
  {
    title: "Shorts",
    icon: "video_library",
  },
  {
    title: "Subscriptions",
    icon: "subscriptions",
  },
  {
    title: "Watch Later",
    icon: "history",
  },
];

const leftDrawerOpen = ref(false);

function toggleLeftDrawer() {
  leftDrawerOpen.value = !leftDrawerOpen.value;
}

const searchQuery = ref();
function search(value) {
  searchQuery.value = "";
}
</script>
