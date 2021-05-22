<template>
    <v-list nav dense >
          <v-list-item-group v-model="group" active-class="deep-purple--text text--accent-4">
            <v-list-item>
              <v-list-item-icon>
                <v-icon>mdi-account-box</v-icon>
              </v-list-item-icon>
              <v-list-item-title>Contacs</v-list-item-title>
            </v-list-item>

            <v-list-item>
              <v-list-item-icon>
                <v-icon>mdi-bookmark</v-icon>
              </v-list-item-icon>
              <v-list-item-title>Saved Messages</v-list-item-title>
            </v-list-item>
            
            <v-list-item>
              <v-list-item-icon>
                <v-icon>mdi-cog</v-icon>
              </v-list-item-icon>
              <v-list-item-title>Setting</v-list-item-title>
            </v-list-item>
            
            <v-list-item>
              <v-list-item-icon>
                <v-icon>mdi-account-plus</v-icon>
              </v-list-item-icon>
              <v-list-item-title>InviteFriends</v-list-item-title>
            </v-list-item>
            
            <v-list-item>
              <v-list-item-icon>
                <v-icon>mdi-shield-half-full</v-icon>
              </v-list-item-icon>
              <v-list-item-title>Proxy</v-list-item-title>
            </v-list-item>
            
            <v-list-item>
              <v-list-item-icon>
                <v-icon>mdi-help-circle</v-icon>
              </v-list-item-icon>
              <v-list-item-title>Help</v-list-item-title>
            </v-list-item>
            
            <v-list-item  @click="$vuetify.theme.dark = !$vuetify.theme.dark">
              <v-list-item-icon>
                <v-icon>mdi-moon-waxing-crescent</v-icon>
              </v-list-item-icon>
              <v-list-item-title>Night Mode</v-list-item-title>
            </v-list-item>
            
          </v-list-item-group>
        </v-list>
</template>