<template>
  <v-app>

    <!--:src="getImgUrl('bk/md-grey-1.png')"-->
    <img class="rsi-background" />

    <v-app-bar app color="grey lighten-3">

      <v-toolbar-title class="tool-bar-title headline blue--text">
        Retail Execution Portal
      </v-toolbar-title>

      <v-spacer></v-spacer>

      <!--solo-->
      <!--single-line
      outlined-->
      <v-text-field
        class="text-field-search-header"
        v-model="search_msg"
        @input="onChangeSearch()"
        placeholder="Search">
      </v-text-field>

      <v-combobox
        class="combo-box-domain"
        v-model="select_domain"
        :items="domains">
      </v-combobox>

      <!--class="avatar-tool-bar blue-grey darken-2 orange&#45;&#45;text app-settings"-->
      <v-avatar
        @click="onShowUserSettingsDialog"
        size="36"
        class="avatar-tool-bar blue-grey darken-2 orange--text app-settings"
      >
        <span>{{ userLetter }}</span>
      </v-avatar>

    </v-app-bar>

    <v-content>
      <router-view/>
    </v-content>

    <!--@click="$router.push('/main-dashboard')"-->
    <!--width="270"-->
    <!---->
    <!--color="grey darken-1"-->
    <!--color="primary"-->
    <v-navigation-drawer
      class="left-vertical-bar"
      v-model="drawer"
      color="primary"
      :mini-variant="mini"
      :right="right"
      absolute
      dark>
      <v-list  class="py-0" >

        <img
          class="rsi-logo"
          :src="getImgUrl('bk/rsi-logo.jpg')" >

        <v-divider></v-divider>

        <v-list-item
          class="vertical-menu"
          v-for="item in items"
          :key="item.title"
          @click="onItemClick(item)">
          <v-icon class="icons-projects" >{{ item.icon }}</v-icon>
          <span class="icon-text" :style="item.marginLeft">{{ item.short }}</span>
        </v-list-item>

      </v-list>
    </v-navigation-drawer>

    <!--v-if="user!==null"-->
    <app-settings-dialog
      :show_dlg="show_setting_dlg"
      v-on:onCloseUserSettingsDialog="onCloseUserSettingsDialog">
    </app-settings-dialog>

    <v-footer class="app-footer" color="grey lighten-3">
      <v-spacer></v-spacer>
      <div>RSi &copy; {{ new Date().getFullYear() }}</div>
    </v-footer>

  </v-app>
</template>

<script>
  import loadImageMixin from "@/mixins/loadImageMixin";
  import AppSettingsDialog from "@/dialogs/app-settings-dialog";

export default {
  name: 'App',
  mixins: [loadImageMixin],
  components: {
    "app-settings-dialog": AppSettingsDialog
  },
  data() {
    return {
      user: 'Kevin Lunn',
      search_msg: "",
      show_setting_dlg: false,
      select_domain: "Americas",
      domains: [
        "Americas", "EU", "CN", "WM", "WM EU", "WM CN"
      ],
      items: [
        { title: 'Retail Execution Portal', short: "REP",
          marginLeft: "margin-left: 3px;", icon: 'category' },
        { title: 'Retail Visibility', short: "RV",
          marginLeft: "margin-left: 5px;", icon: 'visibility' },
        { title: 'Retail Intelligence', short: "RI",
          marginLeft: "margin-left: 6px;", icon: 'share' },
        { title: 'Administration', short: "Admin",
          marginLeft: "margin-left: -3px;", icon: 'person' },
        { title: 'Data Extract Mgmt', short: "DEM",
          marginLeft: "margin-left: 1px;", icon: 'dns'},
        { title: 'Tableau', short: "Tableau",
          marginLeft: "margin-left: -6px;", icon: 'timeline'},
        { title: 'Data Availability', short: "Data",
          marginLeft: "margin-left: 1px;", icon: 'signal_cellular_alt'},
        { title: 'Power BI', short: "Power",
          marginLeft: "margin-left: -2px;", icon: 'insert_chart_outlined'},
        { title: 'OSA Power', short: "OSA",
          marginLeft: "margin-left: 1px;", icon: 'brightness_5'},
        { title: 'Promo Power', short: "Promo",
          marginLeft: "margin-left: -3px;", icon: 'spa'},
        { title: 'Pacific', short: "Pacific",
          marginLeft: "margin-left: -3px;", icon: 'touch_app'}
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
  computed: {
    userLetter() {
      return this.user !== null ? this.user[0] : "";
      // let user = this.$store.getters.getUser;
      // return user !== {} ? user.first_name[0] : "";
    }
  },
  methods: {
    onItemClick(item) {
      console.log('onItemClick(item): ', item );
    },
    onShowUserSettingsDialog() {
      console.clear();
      console.log("onShowUserSettingsDialog()");
      this.show_setting_dlg = true;
    },
    onCloseUserSettingsDialog() {
      console.log("onCloseUserSettingsDialog()");
      this.show_setting_dlg = false;
    },
    onChangeSearch() {
      console.log("onChangeSearch(search): ", this.search_msg);
    }
  }
};
</script>

<style lang="scss">
  .left-vertical-bar {
    //top: 9px !important;
    position: fixed !important;

    .v-list-item--link:before {
      margin-bottom: -9px;
    }

    .vertical-menu {
      margin-top: 3px;
      margin-left: -2px;
      min-height: 51px;

      .icons-projects {}

      .icon-text {
        font-size: 11px;
        position: absolute !important;
        white-space: nowrap;
        display: initial;
        margin-top: 21px;
        overflow: visible !important;
        clip: unset !important;
        height: unset !important;

        //color: black !important;
      }
  }
}

.combo-box-domain {
  top: 9px;
  flex: inherit !important;
  width: 105px;
  right: 42px;
}

.text-field-search-header {
  margin-top: 16px !important;
  flex: inherit !important;
  width: 240px;
  margin-right: 81px !important;
}

.avatar-tool-bar {
  text-align: center;
  margin-top: -9px;
}

.label-name,
.label-logout {
  top: 6px;
}

.app-settings {
  top: 4px;
  &:hover {
    cursor: pointer;
  }
}
.v-toolbar {
  left: 56px !important;
  box-shadow: none !important;
  -webkit-box-shadow:  none !important;
}

.tool-bar-title {
  //margin-top: 9px;
  margin-left: 24px;
}

.rsi-logo {
  height: 27px;
  margin-left: 9px;
  margin-top: 15px;
  margin-bottom: 6px;
  box-shadow: 3px 3px 9px rgba(0, 0, 0, 0.3);

  &:hover {
    //cursor: pointer;
  }
}

.rsi-background {
  //background-image: url("assets/material-design/md-005.jpg");
  //background-image: url("assets/material-design/md-1.jpeg");
  //background-image: url("assets/material-design/md-1-gey.png");
  //background-image: url("assets/material-design/md-015.jpg");

  background-image: url("assets/material-design/md-014.jpg");
  height: 100%;
  width: 100%;
  position: fixed;

  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;

  top: 0;
  left: 0;
}

.app-footer {
  background-color: #ffffff !important;
  position: fixed !important;
  bottom: 0;
  width: 100%;
}

</style>
