<template>
  <div class="dashboard-container">
    <component :is="currentRole" />
  </div>
</template>

<script>
import { mapGetters } from 'vuex'
import adminMenu from './admin'
import editorMenu from './editor'

export default {
  name: 'Menu',
  components: { adminMenu, editorMenu },
  data() {
    return {
      currentRole: 'adminMenu'
    }
  },
  computed: {
    ...mapGetters([
      'roles'
    ])
  },
  created() {
    if (!this.roles.includes('admin')) {
      this.currentRole = 'editorMenu'
    }
  }
}
</script>
