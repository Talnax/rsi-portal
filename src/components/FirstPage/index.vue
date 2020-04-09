<template>
    <div class="first-page">
        <v-timeline class="center">
            <!--color="cyan"-->
            <v-timeline-item
                color="cyan"
                right>
                <v-card>
                    <v-card-title class="cyan">
                        <span class="title font-weight-light white--text ">Knowledge Hub</span>
                        <div class="spacer"></div>
                        <v-icon dark right >
                            mdi-account-multiple-outline
                        </v-icon>
                    </v-card-title>
                    <v-container>
                        <v-row>
                            <v-col class="hidden-sm-and-down" md="2">
                                <v-icon size="33">mdi-account-multiple-outline</v-icon>
                            </v-col>
                            <v-col cols="12" md="10">
                                Knowledge Hub - scaevola imperdiet nec ut,
                                sed euismod convenire principes at.
                                Est et nobis iisque percipit.
                            </v-col>
                        </v-row>
                    </v-container>
                </v-card>
            </v-timeline-item>

            <!--color="amber darken-1"-->
            <v-timeline-item
                color="amber darken-1"
                left>
                <v-card>
                    <v-card-title class="amber darken-1">
                        <span class="title font-weight-light white--text ">Events</span>
                        <div class="spacer"></div>
                        <v-icon dark right >
                            event_available
                        </v-icon>
                    </v-card-title>
                    <v-container>
                        <v-row>
                            <v-col class="hidden-sm-and-down" md="2">
                                <v-icon size="33">event_available</v-icon>
                            </v-col>
                            <v-col cols="12" md="10">
                                Events -  Scaevola imperdiet nec ut,
                                sed euismod convenire principes at. Est et nobis iisque percipit,
                                an vim zril disputando.
                            </v-col>
                        </v-row>
                    </v-container>
                </v-card>
            </v-timeline-item>

            <!--color="purple"-->
            <v-timeline-item
                color="light-blue"
                right>
                <v-card>
                    <v-card-title class="light-blue">
                        <span class="title font-weight-light white--text ">Data Availability</span>
                        <div class="spacer"></div>
                        <v-icon dark right >
                            storage
                        </v-icon>
                    </v-card-title>
                    <v-container>
                        <v-row>
                            <v-col class="hidden-sm-and-down" md="2">
                                <v-icon size="33">storage</v-icon>
                            </v-col>
                            <v-col cols="12" md="10">
                                Data Availability - Imperdiet nec ut,
                                sed euismod convenire principes at iisque percipit,
                                an vim zril disputando voluptatibus.
                            </v-col>
                        </v-row>
                    </v-container>
                </v-card>
            </v-timeline-item>


        </v-timeline>

    </div>
</template>

<script>
    export default {
        name: "index"
    }
</script>

<style lang="scss">
    .first-page {

        .center {
            margin: auto;
            width: 74%;
            /*border: 3px solid green;*/
            //padding: 100px;
            padding: 60px 6px;
        }

        .v-card__title {
            padding: 9px 15px !important;
        }

        .v-timeline:before {
            top: 150px;
            height: 53% !important;
            position: absolute;
        }
    }

</style>