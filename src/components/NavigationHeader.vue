<template>
  <span>
    <v-navigation-drawer app v-model="drawer" dark disable-resize-watcher>
      <v-list>
        <template v-for="(item, index) in items">
          <v-list-tile :key="index" :to="item.id">
            <v-list-tile-content>{{item.title}}</v-list-tile-content>
          </v-list-tile>
          <v-divider :key="`divider-${index}`"></v-divider>
        </template>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar app dark class="nav-header">
      <v-toolbar-side-icon class="hidden-md-and-up" @click="drawer = !drawer"></v-toolbar-side-icon>
      <v-spacer class="hidden-md-and-up"></v-spacer>
      <router-link to="/">
        <v-toolbar-title to="/">{{appTitle}}</v-toolbar-title>
      </router-link>
      <v-spacer class="hidden-sm-and-down"></v-spacer>
      <v-btn flat class="hidden-sm-and-down" to="/sign-in">SIGN IN</v-btn>
      <v-btn color="lighten-1" class="hidden-sm-and-down join-button" to="/join">JOIN</v-btn>
    </v-toolbar>
  </span>
</template>
<script>
export default {
  name: "NavigationHeader",
  data() {
    return {
      appTitle: "DM Table Tool",
      drawer: false,
      items: [
        { title: "Sign In", id: "/sign-in" },
        { title: "Join", id: "/join" }
      ]
    };
  }
};
</script>
<style scoped>
a {
  color: white;
  text-decoration: none;
}

.nav-header {
  background: #003b70;
}

.join-button {
  background: #c72819 !important;
}
</style>
