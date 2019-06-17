<template>
  <div>
    <!--Sidebar-->
    <v-navigation-drawer
    v-model="drawer"
    :mini-variant.sync="mini"
    :clipped="$vuetify.breakpoint.lgAndUp"
    fixed
    app
    >
    <v-toolbar flat class="transparent">
      <v-list class="pa-0">
        <v-list-tile avatar>
          <v-list-tile-avatar>
            <img src="https://randomuser.me/api/portraits/men/85.jpg">
          </v-list-tile-avatar>

          <v-list-tile-content>
            <v-list-tile-title>John Leider</v-list-tile-title>
          </v-list-tile-content>

          <v-list-tile-action>
            <v-btn
              icon
              @click.stop="mini = !mini"
            >
              <v-icon>chevron_left</v-icon>
            </v-btn>
          </v-list-tile-action>
        </v-list-tile>
      </v-list>
    </v-toolbar>

    <v-list class="pt-0" dense>
      <v-divider></v-divider>

      <v-list-tile
        v-for="item in items"
        :key="item.title"
      >
        <v-list-tile-action>
          <v-icon>{{ item.icon }}</v-icon>
        </v-list-tile-action>

        <v-list-tile-content>
          <v-list-tile-title>{{ item.title }}</v-list-tile-title>
        </v-list-tile-content>
      </v-list-tile>
    </v-list>
  </v-navigation-drawer>
    <!--Toolbar - Header -->
    <v-toolbar :clipped-left="$vuetify.breakpoint.lgAndUp" color="teal lighten-1" dark app fixed>
      <v-toolbar-title style="width: 300px" class="ml-0 pl-3">
        <span class="hidden-sm-and-down">Vue Front</span>
        <v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn icon>
        <v-icon>apps</v-icon>
      </v-btn>
      <v-btn icon>
        <v-icon>notifications</v-icon>
      </v-btn>

      <!--Edit Card Profile -->
      <div class="text-xs-center">
        <v-menu v-model="menu" :close-on-content-click="false" :nudge-width="200" offset-x>
          <template v-slot:activator="{ on }">
            <v-btn icon large v-on="on">
                <v-avatar size="32px" tile>
                    <img src="https://cdn.vuetifyjs.com/images/logos/logo.svg" alt="Vuetify">
                </v-avatar>
            </v-btn>
          </template>

          <v-card>
            <v-list>
              <v-list-tile avatar>
                <v-list-tile-avatar>
                  <img src="https://cdn.vuetifyjs.com/images/john.jpg" alt="John">
                </v-list-tile-avatar>

                <v-list-tile-content>
                  <v-list-tile-title>John Leider</v-list-tile-title>
                  <v-list-tile-sub-title>Founder of Vuetify.js</v-list-tile-sub-title>
                </v-list-tile-content>
              </v-list-tile>
            </v-list>

            <v-divider></v-divider>

            <v-list>
              <v-list-tile>
                <v-list-tile-title>Perfil</v-list-tile-title>
              </v-list-tile>

              <v-list-tile>
                <v-list-tile-title>Alertas</v-list-tile-title>
              </v-list-tile>
            </v-list>

            <v-card-actions>
              <v-spacer></v-spacer>

              <v-btn color="error" flat @click="menu = false">Sair</v-btn>
            </v-card-actions>
          </v-card>
        </v-menu>
      </div>
    </v-toolbar>
  </div>
</template>
<script>
export default {
  name: "Header",
  data: () => ({
    drawer: true,
    fav: true,
    menu: false,
    message: false,
    hints: true,
    mini: true,
    right: null,
    items: [
          { title: 'Dashboard', icon: 'dashboard' },
          { title: 'Monitoramento', icon: 'question_answer' }
        ],
  })
};
</script>

