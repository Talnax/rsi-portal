<template>
  <v-app>
    <v-app-bar app color="white">

      <v-toolbar-title class="tool-bar-title headline blue--text">
        Retail Execution Portal
      </v-toolbar-title>

      <v-spacer></v-spacer>

      <!--solo-->
      <!--single-line
      outlined-->
      <v-text-field
        class="text-field-search-header"
        placeholder="Search">
      </v-text-field>

      <v-combobox
        class="combo-box-domain"
        v-model="select_domain"
        :items="domains">
      </v-combobox>

      <v-avatar
        @click="onShowUserSettingsDialog"
        size="36"
        class="avatar-tool-bar blue-grey darken-2 orange--text app-settings">
        <span>{{ userLetter }}</span>
      </v-avatar>

    </v-app-bar>

    <v-content>
      <router-view/>
    </v-content>

    <!--@click="$router.push('/main-dashboard')"-->
    <!--width="270"-->
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
          <!--<span class="icon-text">{{ item.title }}</span>-->
          <!--<span class="icon-text">{{ item.short }}</span>-->
          <span class="icon-text" v-bind:style="item.marginLeft">{{ item.short }}</span>
        </v-list-item>

      </v-list>
    </v-navigation-drawer>

    <!--v-if="user!==null"-->
    <app-settings-dialog
      :show_dlg="show_setting_dlg"
      v-on:onCloseUserSettingsDialog="onCloseUserSettingsDialog">
    </app-settings-dialog>

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
      show_setting_dlg: false,
      select_domain: "Americas",
      domains: [
        "Americas", "India"
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
    }
  }
};
</script>

<style lang="scss">
  .left-vertical-bar {
    //top: 9px !important;

    .vertical-menu {
      //min-height: 55px !important;
      min-height: 51px;

      /*.v-list-item--dense, .v-list--dense .v-list-item {*/
        /*min-height: 45px;*/
      /*}*/

      .icons-projects {
        //min-height: 35px !important;
      }

      .icon-text {
        font-size: 11px;
        position: absolute !important;
        white-space: nowrap;
        display: initial;
        margin-top: 21px;
        overflow: visible !important;
        clip: unset !important;
        height: unset !important;
      }
  }
}







.combo-box-domain {
  top: 15px;
  flex: inherit !important;
  width: 105px;
  right: 42px;
}

.text-field-search-header {
  margin-top: 30px !important;
  flex: inherit !important;
  width: 150px;
  margin-right: 81px !important;
}

.avatar-tool-bar {
  text-align: center;
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
  margin-top: 15px;
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

</style>
