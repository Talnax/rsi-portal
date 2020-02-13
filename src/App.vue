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

      <v-layout align-center justify-end row fill-height>
        <v-flex xs12 sm6 >
          <!--<label class="domain-name" >Domain:</label>-->
          <!--label="Domain"-->
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

    <!--width="270"-->
    <!--:mini-variant="miniVariant"-->
    <v-navigation-drawer
      class="left-vertical-bar"
      v-model="drawer"
      color="primary"
      :mini-variant="mini"
      :right="right"
      absolute
      dark>
      <v-list
        dense
        nav
        class="py-0" >
        <v-divider></v-divider>
        <v-list-item
          v-for="item in items"
          :key="item.title"
          @click="onItemClick(item)"
          link >
          <v-tooltip right>
            <template v-slot:activator="{ on }">
            <!--<v-list-item-icon>-->
              <v-icon v-on="on">{{ item.icon }}</v-icon>
            <!--</v-list-item-icon>-->
            </template>
            <span>{{ item.title }}</span>
          </v-tooltip>

          <!--<v-list-item-content>-->
            <!--<v-list-item-title>{{ item.title }}</v-list-item-title>-->
          <!--</v-list-item-content>-->
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

  </v-app>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {

      select_domain: "Americas",
      domains: [
        "Americas", "India"
      ],
      items: [
        { title: '000', icon: '' },
        { title: '111', icon: '' },
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
      right: null,
      mini: true,
      drawer: true,
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
  .left-vertical-bar {
    top: 9px !important;
  }
  .domain-name {
    position: absolute;
    top: 18px;
    font-size: 1.2rem;
  }
  .combo-box-domain {
    width: 96px;
    top: 8px;
    right: -72px;
    margin-top: 12px;
  }

</style>
