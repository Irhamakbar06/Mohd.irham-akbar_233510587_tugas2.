<template>
  <div class="sidebar">
    <h2>Pertemuan 2 dan 3</h2>
    <ul>
      <li
        v-for="item in menuItems"
        :key="item.component"
        @click="$emit('change-page', item.component)"
      >
        {{ item.name }}
      </li>
    </ul>
  </div>
</template>

<script setup>
const menuItems = [
  { name: 'Home', component: 'Home' },
  { name: 'Declarative Rendering', component: 'DeclarativeRendering' },
  { name: 'Attribute Bindings', component: 'AttributeBindings' },
  { name: 'Form Bindings', component: 'FormBindings' },
  { name: 'Conditional Rendering', component: 'ConditionalRendering' },
  { name: 'List Rendering', component: 'ListRendering' },
  { name: 'Computed Property', component: 'ComputedProperty' },
  { name: 'Lifecycle dan Template Refs', component: 'LifecycleandTemplateRefs' },
  { name: 'Watchers', component: 'Watchers' }
]
</script>

<style scoped>
.sidebar {
  width: 250px;
  background-color: #2c3e50;
  color: white;
  padding: 30px 20px;
  box-shadow: 2px 0 5px rgba(0, 0, 0, 0.1);
  position: sticky;
  top: 0;
  height: 100vh;
}

.sidebar h2 {
  font-size: 20px;
  margin-bottom: 20px;
  border-bottom: 1px solid #7f8c8d;
  padding-bottom: 10px;
}

.sidebar ul {
  list-style: none;
  padding: 0;
}

.sidebar li {
  margin: 12px 0;
  cursor: pointer;
  padding: 8px 12px;
  border-radius: 5px;
  transition: background 0.2s;
}

.sidebar li:hover {
  background-color: #34495e;
}
</style>
