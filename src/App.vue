<template>
  <v-app>
    <v-app-bar
      app
      color="white">

      <!--<v-btn icon>-->
        <!--<v-icon>menu</v-icon>-->
      <!--</v-btn>-->

      <v-app-bar-nav-icon
        @click="onMenuClick()">
      </v-app-bar-nav-icon>

      <v-toolbar-title style="">Retail Execution Portal</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-layout v-layout align-center justify-end row fill-height>
        <v-flex xs12 sm6 >
          <label class="domain-name" >Domain:</label>
          <v-combobox
            class="combo-box-domain"
            v-model="select_domain"
            :items="domains"
          ></v-combobox>

        </v-flex>
      </v-layout>

      <v-btn
        href="https://"
        target="_blank"
        text>
        <span class="mr-2">Kevin Lunn</span>
      </v-btn>

      <v-btn
          href="https://github.com/vuetifyjs/vuetify/releases/latest"
          target="_blank"
          text>
        <span class="mr-2">Logout</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>

    </v-app-bar>

    <v-content>
      <!--<router-view/>-->
    </v-content>

    <v-navigation-drawer
      class="left-bar"
      width="270"
      v-model="drawer"
      color="primary"
      :mini-variant="miniVariant"
      :right="right"
      absolute
      dark>
      <v-list
        dense
        nav
        class="py-0" >
        <!--<v-list-item two-line :class="miniVariant && 'px-0'">-->
          <!--<v-list-item-avatar>-->
            <!--<img src="https://randomuser.me/api/portraits/men/81.jpg">-->
          <!--</v-list-item-avatar>-->

          <!--<v-list-item-content>-->
            <!--<v-list-item-title>123456</v-list-item-title>-->
            <!--<v-list-item-subtitle>Subtext</v-list-item-subtitle>-->
          <!--</v-list-item-content>-->
        <!--</v-list-item>-->

        <v-divider></v-divider>

        <v-list-item
          v-for="item in items"
          :key="item.title"
          @click="onItemClick(item)"
          link >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

  </v-app>
</template>

<script>
//import HelloWorld from './components/HelloWorld';

export default {
  name: 'App',
  data() {
    return {
      drawer: true,
      select_domain: "Americas",
      domains: [
        "Americas", "India"
      ],
      items: [
        { title: 'Retail Execution Portal', icon: 'category' },
        { title: 'Retail Visibility', icon: 'visibility' },
        { title: 'Retail Entelligence', icon: 'share' },
        { title: 'Administration', icon: 'person' },
        { title: 'Data Extract Mgmt', icon: 'dns'},
        { title: 'Tableau', icon: 'timeline'},
        { title: 'Data Availability', icon: 'signal_cellular_alt'},
        { title: 'Power BI', icon: 'insert_chart_outlined'},
        { title: 'OSA Power', icon: 'brightness_5'},
        { title: 'Promo Power', icon: 'spa'},
        { title: 'Pacific', icon: 'touch_app'}
      ],
      // color: 'primary',
      // colors: [
      //   'primary',
      //   'blue',
      //   'success',
      //   'red',
      //   'teal',
      // ],
      right: false,
      miniVariant: true
    };
  },
  methods: {
    onItemClick(item) {
      console.log('onItemClick(item): ', item );
    },
    onMenuClick() {
      console.log('onMenuClick() ' );
    }
  }
};
</script>

<style lang="scss">
  .domain-name {
    position: absolute;
    top: 18px;
    font-size: 1.2rem;
  }
  .combo-box-domain {
    /*font-size: 14px !important;*/
    width: 96px;
    /* left: 15px; */
    top: 6px;
    /* right: 33px; */
    right: -81px;
    margin-top: 12px;
  }

</style>
