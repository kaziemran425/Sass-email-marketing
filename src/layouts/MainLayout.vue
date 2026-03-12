<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated class="bg-white">
      <q-toolbar>
        <q-btn
          flat
          color="teal-7"
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title>
          <div class="text-teal text-weight-bold text-h5">Email Marketing</div>
        </q-toolbar-title>

        <div class="q-pa-md gt-sm">
          <div class="row item-center q-gutter-sm">
            <q-btn flat label="Home" no-caps color="teal-7" @click="scrollToElement('home')" />
            <q-btn flat label="Features" no-caps color="teal-7" @click="scrollToElement('features')" />
            <q-btn flat label="Pricing" no-caps color="teal-7" @click="scrollToElement('pricing')" />
            <q-btn flat label="Contact" no-caps color="teal-7" @click="scrollToElement('contact')" />
          </div>
        </div>

        <div class="q-pa-md">
          <div class="row items-center q-gutter-sm">
            <q-btn
              dense
              label="Login"
              outline
              no-caps
              color="teal-7"
              to="/login"
              class="q-px-sm"
            />
            <q-btn
              dense
              label="Start Free Trial"
              no-caps
              color="teal-7"
              to="/login"
              class="q-px-sm"
            />
          </div>
        </div>
      </q-toolbar>
    </q-header>

    <q-drawer v-model="leftDrawerOpen" show-if-above bordered>
      <q-list>
        <q-item-label header> Essential Links </q-item-label>
        <EssentialLink
          v-for="link in linksList"
          :key="link.title"
          v-bind="link"
        />

        <q-separator class="q-my-md"/>
        <q-item-label header> Navigation </q-item-label>
        <q-item clickable v-ripple @click="scrollToElement('home')"><q-item-section>Home</q-item-section></q-item>
        <q-item clickable v-ripple @click="scrollToElement('features')"><q-item-section>Features</q-item-section></q-item>
        <q-item clickable v-ripple @click="scrollToElement('pricing')"><q-item-section>Pricing</q-item-section></q-item>
        <q-item clickable v-ripple @click="scrollToElement('contact')"><q-item-section>Contact</q-item-section></q-item>
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from "vue";
import { useRouter, useRoute } from "vue-router";
import { scroll } from "quasar";
import EssentialLink from "components/EssentialLink.vue";

const { getScrollTarget, setVerticalScrollPosition } = scroll;

const linksList = [
  { title: "Docs", caption: "quasar.dev", icon: "school", link: "https://quasar.dev" },
  { title: "Github", caption: "github.com/quasarframework", icon: "code", link: "https://github.com/quasarframework" },
  { title: "Discord", caption: "chat.quasar.dev", icon: "chat", link: "https://chat.quasar.dev" },
];

export default defineComponent({
  name: "MainLayout",
  components: { EssentialLink },
  setup() {
    const leftDrawerOpen = ref(false);
    const router = useRouter();
    const route = useRoute();

    // Smooth Scroll Logic
    const scrollToElement = (id) => {
      // If we are not on the index page (e.g., we are on /login), navigate back to '/' first
      if (route.path !== '/') {
        router.push('/').then(() => {
          setTimeout(() => executeScroll(id), 300); // Wait 300ms for page to render before scrolling
        });
      } else {
        // If already on index page, just scroll
        executeScroll(id);
      }
    };

    const executeScroll = (id) => {
      const el = document.getElementById(id);
      if (el) {
        const target = getScrollTarget(el);
        const offset = el.offsetTop - 60; // Offset by 60px so the sticky header doesn't cover the title
        const duration = 500; // Scroll animation time in milliseconds
        setVerticalScrollPosition(target, offset, duration);

        // Auto-close drawer on mobile devices after clicking a link
        if (window.innerWidth < 1024) {
           leftDrawerOpen.value = false;
        }
      }
    };

    return {
      linksList,
      leftDrawerOpen,
      scrollToElement,
      toggleLeftDrawer() {
        leftDrawerOpen.value = !leftDrawerOpen.value;
      },
    };
  },
});
</script>
