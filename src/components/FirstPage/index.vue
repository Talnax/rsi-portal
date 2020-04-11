<template>
    <div class="first-page">
        <v-timeline class="centrium">
            <!--color="cyan"-->
            <v-timeline-item
                color="indigo"
                right>
                <v-card>
                    <v-card-title class="indigo">
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
                            </v-col>
                        </v-row>
                    </v-container>
                </v-card>
            </v-timeline-item>

            <!--color="amber darken-1"-->
            <v-timeline-item
                color="cyan"
                left>
                <v-card>
                    <v-card-title class="cyan">
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
                                sed euismod convenire principes at.
                                Est et nobis iisque percipit.
                            </v-col>
                        </v-row>
                    </v-container>
                </v-card>
            </v-timeline-item>

            <!--light-blue-->
            <v-timeline-item
                color="blue"
                right>
                <v-card>
                    <v-card-title class="blue">
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
                                an vim zril.
                            </v-col>
                        </v-row>
                    </v-container>
                </v-card>
            </v-timeline-item>

            <div class="main-title display-3">
                <b class="indigo--text position-1">K</b>nowledge<br><br>
                <b class="cyan--text position-2">E</b>vents <br><br>
                <b class="blue--text position-3">D</b>ata
            </div>

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

        .centrium {
            margin: auto;
            width: 51%;
            left: 240px;
            top: 60px;

            .main-title {
                position: absolute;
                top: 90px;
                left: -420px;
                white-space: normal;
                font-size: 3.6rem !important;

                .position-1 {
                    margin-left: -24px;
                }

                .position-2 {

                }

                .position-3 {
                    margin-left: 24px;
                }
            }
        }

        .v-card__title {
            //padding: 9px 15px !important;
            padding: 6px 15px !important;
        }

        .v-timeline:before {
            top: 110px;
            height: 63% !important;
            position: absolute;
        }

        .v-timeline-item {
            padding-bottom: 0 !important;
        }
    }

</style>