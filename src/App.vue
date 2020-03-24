<template>
  <v-app>
    <v-app-bar app color="white">

      <v-toolbar-title class="tool-bar-title headline blue--text">
        Retail Execution Portal
      </v-toolbar-title>

      <v-spacer></v-spacer>

      <v-text-field
        class="text-field-search-header"
        label="Search">
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
      <!--<v-list dense nav class="py-0" >-->
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
          <span class="icon-text">{{ item.title }}</span>
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
        { title: 'Retail Execution Portal', icon: 'category' },
        { title: 'Retail Visibility', icon: 'visibility' },
        { title: 'Retail Intelligence', icon: 'share' },
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

      /*.v-list-item--dense, .v-list--dense .v-list-item {*/
        /*min-height: 45px;*/
      /*}*/

      .icons-projects {
        //min-height: 35px !important;
      }
      .icon-text {
        /*margin-top: 3px;*/
        /*text-align: center;*/
        /*height: auto;*/
        /*width: auto;*/
        /*z-index: 100;*/
        /*color: white;*/
        /*font-size: 10px;*/
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
    margin-right: 81px;
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
