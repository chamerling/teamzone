<template>
  <v-app id="example-2" toolbar>
    <v-navigation-drawer absolute persistent light :mini-variant.sync="mini" v-model="drawer" overflow>
      <v-toolbar flat class="transparent">
        <v-list class="pa-0">
          <v-list-tile avatar>
            <v-list-tile-avatar>
              <img src="https://randomuser.me/api/portraits/lego/1.jpg" />
            </v-list-tile-avatar>
            <v-list-tile-content>
              <v-list-tile-title>Christophe Hamerling</v-list-tile-title>
            </v-list-tile-content>
            <v-list-tile-action>
              <v-btn icon @click.native.stop="mini = !mini">
                <v-icon>chevron_left</v-icon>
              </v-btn>
            </v-list-tile-action>
          </v-list-tile>
        </v-list>
      </v-toolbar>
      <v-list class="pt-0" dense>
        <v-divider></v-divider>
        <v-list-tile v-for="item in items" :key="item.title" @click="">
          <v-list-tile-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title>{{ item.title }}</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar fixed class="blue" dark>
      <v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
      <v-toolbar-title>Teamzone</v-toolbar-title>
    </v-toolbar>
    <main>
      <v-container fluid>
        <div class="title">Click on sidebar to re-open.</div>
        <router-view></router-view>
      </v-container>
    </main>
  </v-app>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      drawer: true,
      items: [
        { title: 'Home', icon: 'dashboard' },
        { title: 'About', icon: 'question_answer' }
      ],
      mini: false,
      right: null
    }
  }
}
</script>

<style lang="styl">

#app
  font-family: 'Roboto', 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased
  -moz-osx-font-smoothing: grayscale
  text-align: center
  margin-top: 0

</style>