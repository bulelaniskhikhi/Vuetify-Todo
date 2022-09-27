
<template>
  <v-app id="inspire">
    <v-navigation-drawer 
    v-model="drawer"
    app
    >
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="text-h6">
            Xena To Do
          </v-list-item-title>
          <v-list-item-subtitle>
            Best to do ever
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list
        dense
        nav
      >
        <v-list-item
          v-for="item in items"
          :key="item.title"
          :to="item.to"
          link
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar
      app
      color="#f5f5f5"
      dark
      shrink-on-scroll
      
      scroll-target="#scrolling-techniques-2"
    >
      <template v-slot:img="{ props }">
        
      </template>

      <v-app-bar-nav-icon style="color: black" @click="drawer = !drawer" ></v-app-bar-nav-icon>

      <v-app-bar-title style="color: black">Xena Todo</v-app-bar-title>

      <v-spacer></v-spacer>

      <v-btn icon style="color: black">
        <v-icon>mdi-magnify</v-icon>
      </v-btn>

      <v-btn icon style="color: black">
        <v-icon>mdi-heart</v-icon>
      </v-btn>

      <v-btn icon style="color: black">
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      
      <router-view></router-view>
    </v-main>

  </v-app>
</template>

<script>
  export default {
    data: () => ({ 
      drawer: null,
      items: [
          { title: 'Todo', icon: 'mdi-format-list-checks', to: '/' },
          { title: 'About', icon: 'mdi-help-box', to: '/about' },
        ],
    }),
  }
</script>