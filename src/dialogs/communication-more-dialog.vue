<template>
    <div class="communication-more-dialog">
        <div class="text-center">

            <v-dialog
                v-model="show_dlg"
                width="500">

                <v-card>
                    <v-card-title
                        class="headline grey lighten-2"
                        primary-title>
                        Privacy Policy
                    </v-card-title>

                    <v-card-text>
                        Lorem ipsum dolor sit amet, consectetur adipiscing elit,
                        sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris
                        nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in
                        reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
                        pariatur. Excepteur sint occaecat cupidatat non proident, sunt in
                        culpa qui officia deserunt mollit anim id est laborum.
                    </v-card-text>

                    <v-divider></v-divider>

                    <v-card-actions>
                        <v-spacer></v-spacer>
                        <v-btn
                            color="primary"
                            text
                            @click="onCloseDlg">
                            I accept
                        </v-btn>
                    </v-card-actions>
                </v-card>

            </v-dialog>

        </div>
    </div>
</template>

<script>
    export default {
        name: "communication-more-dialog",
        props: ["show_dlg", "show_item"],
        data() {
            return {
                //dialog: false
            }
        },
        methods: {
            onCloseDlg() {
                console.log("communication-more-dialog.onCloseDlg()");
                this.$emit("onCloseCommunicationMoreDialog");
            }
        }
    }
</script>

<style lang="scss">
    .communication-more-dialog {}

</style>