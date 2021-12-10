<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title>
          
        </q-toolbar-title>

        <div>Quasar v{{ $q.version }}</div>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
    >
      <q-list>
        <q-item-label
          header
        >
          MENU <br>
          <p>Setting Control</p>
          <hr>
        </q-item-label>

        <EssentialLink
          v-for="link in essentialLinks"
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

<script>
import EssentialLink from 'components/EssentialLink.vue'



const linksList = [
  {
    title: 'Dashboard',
    caption: '',
    icon: 'school',
    link: 'https://quasar.dev'
  },
  {
    title: 'Compare Stocks',
    caption: '',
    icon: 'code',
    link: 'https://github.com/quasarframework'
  },
  {
    title: '3 Best Stocks',
    caption: '',
    icon: 'chat',
    link: 'https://chat.quasar.dev'
  },
  {
    title: 'Worst Stocks',
    caption: '',
    icon: 'record_voice_over',
    link: 'https://forum.quasar.dev'
  },
  {
    title: 'AI based value stock',
    caption: '',
    icon: 'rss_feed',
    link: 'https://twitter.quasar.dev'
  },
  {
    title: 'Best Performing Stocks',
    caption: '',
    icon: 'public',
    link: 'https://facebook.quasar.dev'
    

  },
  
];

import { defineComponent, ref } from 'vue'



export default defineComponent({
  name: 'MainLayout',

  components: {
    EssentialLink,
    
   
},

  setup () {
    const leftDrawerOpen = ref(false)

    return {
      essentialLinks: linksList,
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }
    }
  }
})
</script>
<style>
.love{
  border-radius: 20px;
}
.q-item__label
          {
            color: white;
          }
           .q-item__label--header{
            text-align: center;
            color: #fff;
            font-weight: bolder;
            font-size: 17px;}
           .q-item__label--header p{
              color:#102B7B;
            
          }
.q-drawer__content{
  background-image: linear-gradient(#529BDE,#254F9B)
}
 .material-icons 
 {
   color: white;
 }

</style>
