<template>
  <nav class="nav flex-column">
    <div class="sidebar-brand d-flex justify-content-between align-items-end">
      <Logo />
      <button class="btn btn-link btn-lg p-0 m-0 d-md-none" @click="store.hideMenu">
        <Icon icon="x" />
      </button>
    </div>

    <router-link class="nav-link" :to="{name: 'home'}" exact>
      <Icon icon="discover" class="" /> Découvrir
    </router-link>

    <router-link class="nav-link" :to="{name: 'queue'}">
      <Icon icon="playlist" /> Lecture
    </router-link>

    <small class="sidebar-heading text-muted">
      Bibliothèque
    </small>

    <router-link class="nav-link" :to="{name: 'albums-default'}">
      <Icon icon="library" /> Albums
    </router-link>

    <router-link class="nav-link" :to="{name: 'artists'}">
      <Icon icon="library" /> Artistes
    </router-link>

    <router-link class="nav-item nav-link" :to="{name: 'genres'}">
      <Icon icon="library" /> Genres
    </router-link>

    <router-link class="nav-link" :to="{name: 'playlists'}">
      <Icon icon="list" /> Listes de lecture
    </router-link>

    <router-link class="nav-link" :to="{name: 'favourites'}">
      <Icon icon="heart" /> Favoris
    </router-link>

    <router-link class="nav-link" :to="{name: 'podcasts'}">
      <Icon icon="podcast" /> Podcasts
    </router-link>

    <router-link class="nav-link" :to="{name: 'radio'}">
      <Icon icon="radio" /> Radios
    </router-link>

    <router-link class="nav-link" :to="{name: 'files'}">
      <Icon icon="files" /> Fichiers
    </router-link>

    <PlaylistNav />
  </nav>
</template>
<script lang="ts">
  import { defineComponent } from 'vue'
  import Logo from './Logo.vue'
  import PlaylistNav from '@/library/playlist/PlaylistNav.vue'
  import { useMainStore } from '@/shared/store'

  export default defineComponent({
    components: {
      Logo,
      PlaylistNav,
    },
    setup() {
      return {
        store: useMainStore(),
      }
    },
  })
</script>
