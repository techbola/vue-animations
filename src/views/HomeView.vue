<template>
  <div class="home">
    <Toast v-if="showToast" />
    <Todos @badValue="triggerToast" />
  </div>
</template>

<script>
import { ref } from 'vue'
import Toast from '../components/ToastComponent.vue'
import Todos from '../components/TodosComponent.vue'

export default {
  components: { Toast, Todos },
  setup() {
    const showToast = ref(false)

    const triggerToast = () => {
      showToast.value = true
      setTimeout(() => (showToast.value = false), 3000)
    }

    return { showToast, triggerToast }
  },
}
</script>

<style></style>
