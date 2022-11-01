<template>
    <nav>

        <v-app-bar
      app
      class="grey lighten-3"
      light
    >
    <v-app-bar-nav-icon class="grey--text"  @click="drawer = !drawer"></v-app-bar-nav-icon>
    
      <v-app-bar-title>
        <span class="grey--text">Project</span>
        <span>Tracker</span>
      </v-app-bar-title>

      <v-spacer></v-spacer> 

      <v-btn text color="grey">
        <span>Sign Out</span>
        <v-icon>mdi-exit-to-app</v-icon>
    </v-btn>

    </v-app-bar>

    <v-navigation-drawer v-model="drawer" app class="grey lighten-3">
        <v-list>
            <v-list-item-group
            v-model="selectedItem"
            >
                <v-list-item
                v-for="(item, i) in items"
            :key="i"
            :to="item.route"
            >
                    <v-list-item-icon>
                        <v-icon v-text="item.icon"></v-icon>
                    </v-list-item-icon>

                    <v-list-item-content>
                        <v-list-item-title v-text="item.text"></v-list-item-title>
                    </v-list-item-content>
                </v-list-item>
            </v-list-item-group>
        </v-list>
    </v-navigation-drawer>
    </nav>
</template>

<script>
export default {
    data() {
        return {
            drawer: false,
            selectedItem: 0,
            items: [
                { text: 'Dashboard', icon: 'mdi-view-dashboard', route:'/'},
                { text: 'My Projects', icon: 'mdi-folder', route:'/project'},
                { text: 'Team', icon: 'mdi-account-group', route:'/team'},
         ],
        }
    }
}
</script>