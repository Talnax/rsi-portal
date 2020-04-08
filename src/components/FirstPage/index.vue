<template>
    <div class="first-page">
        <v-timeline class="center">
            <v-timeline-item
                color="purple lighten-2"
                fill-dot
                right>
                <v-card>
                    <v-card-title class="purple lighten-2">
                        <v-icon
                            dark
                            size="42"
                            class="mr-4">
                            mdi-magnify
                        </v-icon>
                        <h2 class="display-1 white--text font-weight-light">Knowledge Hub</h2>
                    </v-card-title>
                    <v-container>
                        <v-row>
                            <v-col cols="12" md="10">
                                Allison Commune scaevola imperdiet nec ut, sed euismod convenire principes at. Est et nobis iisque percipit.
                            </v-col>
                            <v-col
                                    class="hidden-sm-and-down text-right"
                                    md="2"
                            >
                                <v-icon size="64">mdi-calendar-text</v-icon>
                            </v-col>
                        </v-row>
                    </v-container>
                </v-card>

            </v-timeline-item>

            <v-timeline-item
                color="amber lighten-1"
                fill-dot
                left>
                <v-card>
                    <v-card-title class="amber lighten-1 ">
                        <v-icon
                            dark
                            size="42"
                            class="mr-4">
                            mdi-home-outline
                        </v-icon>
                        <h2 class="display-1 mr-4 white--text font-weight-light">Events</h2>
                        <!--<v-icon-->
                            <!--dark-->
                            <!--size="42">-->
                            <!--mdi-home-outline-->
                        <!--</v-icon>-->
                    </v-card-title>
                    <v-container>
                        <v-row>
                            <v-col class="hidden-sm-and-down" md="2">
                                <v-icon size="64">mdi-server-network</v-icon>
                            </v-col>
                            <v-col cols="12" md="10">
                                Rost, no nam oblique veritus. Commune scaevola imperdiet nec ut,
                                sed euismod convenire principes at. Est et nobis iisque percipit,
                                an vim zril disputando voluptatibus.
                            </v-col>
                        </v-row>
                    </v-container>
                </v-card>
            </v-timeline-item>

            <!--
            <v-timeline-item
                color="cyan lighten-1"
                fill-dot
                right>
                <v-card>
                    <v-card-title class="cyan lighten-1">
                        <v-icon
                            class="mr-4"
                            dark
                            size="42">
                            mdi-email-outline
                        </v-icon>
                        <h2 class="display-1 white--text font-weight-light">Title 3</h2>
                    </v-card-title>
                    <v-container>
                        <v-row>
                            <v-col
                                v-for="n in 3"
                                :key="n"
                                cols="12"
                                md="4">
                                Lorem ipsum dolor sit amet, no nam oblique veritus no nam oblique.
                            </v-col>
                        </v-row>
                    </v-container>
                </v-card>
            </v-timeline-item>
            -->

            <v-timeline-item
                color="cyan lighten-1"
                fill-dot
                right>
                <v-card>
                    <v-card-title class="cyan lighten-1 ">
                        <v-icon
                            dark
                            size="42"
                            class="mr-4">
                            mdi-account-multiple-outline
                        </v-icon>
                        <h2 class="display-1 mr-4 white--text font-weight-light">Data Availability</h2>

                    </v-card-title>
                    <v-container>
                        <v-row>
                            <v-col class="hidden-sm-and-down" md="2">
                                <v-icon size="64">mdi-server-network</v-icon>
                            </v-col>
                            <v-col cols="12" md="10">
                                Rost, no nam oblique veritus. Commune scaevola imperdiet nec ut,
                                sed euismod convenire principes at. Est et nobis iisque percipit,
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
            padding: 90px 6px;
        }

        .v-timeline:before {
            top: 163px;
            height: 53% !important;
            position: absolute;
        }
    }

</style>