<template>
  <div class="app">
    <Sidebar @change-page="currentPage = $event" />
    <div class="content">
      <component :is="currentPageComponent" />
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'
import Sidebar from './components/Sidebar.vue'

import Home from './components/Home.vue'
import DeclarativeRendering from './components/DeclarativeRendering.vue'
import AttributeBindings from './components/AttributeBindings.vue'
import FormBindings from './components/FormBindings.vue'
import ConditionalRendering from './components/ConditionalRendering.vue'
import ListRendering from './components/ListRendering.vue'
import ComputedProperty from './components/ComputedProperty.vue'
import LifecycleandTemplateRefs from './components/LifecycleandTemplateRefs.vue'
import Watchers from './components/Watchers.vue'

const currentPage = ref('Home')

const currentPageComponent = computed(() => {
  const components = {
    Home,
    DeclarativeRendering,
    AttributeBindings,
    FormBindings,
    ConditionalRendering,
    ListRendering,
    ComputedProperty,
    LifecycleandTemplateRefs,
    Watchers
  }
  return components[currentPage.value] || Home
})
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html, body {
  height: 100%;
  width: 100%;
  font-family: 'Segoe UI', sans-serif;
  background-color: #f0f2f5;
}

#app {
  display: flex;
  min-height: 100vh;
  width: 100vw;
}

.app {
  display: flex;
  flex: 1;
}

.content {
  flex: 1;
  padding: 40px;
  background-color: #ffffff;
  overflow-y: auto;
}
</style>

