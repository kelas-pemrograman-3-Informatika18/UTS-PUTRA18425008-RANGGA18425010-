<template>
  <q-layout view="lHh Lpr lFf">
    <q-header unelevated>
      <q-toolbar class="bg-red">
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="leftDrawerOpen = !leftDrawerOpen"
        />

         <q-toolbar-title>
          Aplikasi Mini Market
        </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      content-class="bg-grey-1"
    >
      <q-list>
        <q-item-label
          header
          class="text-grey-8"
        >
          Menu
        </q-item-label>
        <q-item clickable active-class="active" exact v-ripple :to="{name: 'dashboard'}">
          <q-item-section avatar>
              <q-icon name="dashboard" />
          </q-item-section>

          <q-item-section>
             Dashboard
          </q-item-section>
        </q-item>
        <q-item clickable active-class="active" exact v-ripple :to="{name: 'inputData'}">
          <q-item-section avatar>
              <q-icon name="inputData" />
          </q-item-section>

          <q-item-section>
             Input Data
          </q-item-section>
        </q-item>
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
export default {
  name: 'MainLayout',
  data () {
    return {
      leftDrawerOpen: false
    }
  }
}
</script>
