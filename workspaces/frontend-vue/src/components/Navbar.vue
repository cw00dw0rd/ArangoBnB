<template>
  <div>
    <md-toolbar>
      <span class="md-title">ArangoBnB</span>
      <div class="md-toolbar-section-end">
        <md-button>Become a host</md-button>
        <md-button class="md-icon-button">
          <font-awesome-icon class="globe" icon="globe-americas" />
        </md-button>
        <div class="user-area">
          <md-button class="user-icons md-icon-button md-raised">
            <md-icon>person</md-icon>
          </md-button>
          <md-button class="md-icon-button md-raised user-icons">
            <md-icon>menu</md-icon>
          </md-button>
        </div>
      </div>
    </md-toolbar>
  </div>
</template>

<script src="https://kit.fontawesome.com/50530a7384.js" crossorigin="anonymous"></script>
<script>

import Vue from 'vue'
import VueMaterial from 'vue-material'
import 'vue-material/dist/vue-material.min.css'

  export default {
    name: 'Navbar',
    data: () => ({
      showNavigation: false,
      showSidepanel: false
      })
  }
  Vue.use(VueMaterial)

</script>

<style lang="scss" scoped>
  .globe {
    font-size: 16px;
  }

  .user-icon {
    font-size: 22px;
  }

  .user-area {
    background-color: #709554;
    padding: 3px;
    border-radius: 25px;
  }
</style>