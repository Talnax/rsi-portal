<template>
    <div class="first-page">
        <v-timeline class="centrium">
            <!--color="cyan"-->
            <v-timeline-item
                color="indigo"
                right>
                <v-card class="card-style">
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
                <v-card class="card-style">
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
                <v-card class="card-style">
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
                <p><b class="indigo--text position-1">K</b>nowledge<br><br></p>
                <p><b class="cyan--text position-2">E</b>vents <br><br></p>
                <p><b class="blue--text position-3">D</b>ata</p>
            </div>

        </v-timeline>

        <hr class="divider">

        <div class="communication-section">
            <div class="communication-title ">
                <!--<p><b class="cyan--text">C</b>ommunication</p>-->
                <p class="cyan--text"><b class="black--text">C</b>ommunication</p>
            </div>

            <div class="communication-data">
                <div class="communication-item">
                    <v-list class="list-data" two-line>
                        <template v-for="(item, index) in communication">
                            <v-list-item
                                :key="item.title"
                                ripple
                                @click="">
                                <v-list-item-avatar>
                                    <!--<img v-bind:src="item.avatar">-->
                                    <!--<img v-if="item.avatar.filter(x => x.includes('https'))"-->
                                    <img v-if="item.avatar.includes('icons')"
                                         :src="getImgUrl(item.avatar)">
                                    <img v-else :src='item.avatar' >
                                    <!--:src="getImgUrl('icons/rsi-logo.jpg')">-->
                                    <!--:src="getImgUrl('bk/rsi-logo.jpg')"-->
                                </v-list-item-avatar>
                                <v-list-item-content>
                                    <v-list-item-title ><b>{{ item.title }}</b></v-list-item-title>
                                    <v-list-item-subtitle v-html="item.subtitle"></v-list-item-subtitle>
                                </v-list-item-content>
                                <v-spacer></v-spacer>
                                <span>{{item.date}}, {{item.time}}</span>
                            </v-list-item>
                            <v-divider :key="index" inset></v-divider>
                        </template>
                    </v-list>

                </div>
            </div>

        </div>

        <hr class="divider">

    </div>
</template>

<script>
    import loadImageMixin from "@/mixins/loadImageMixin";

    export default {
        name: "index",
        mixins: [loadImageMixin],
        data() {
            return {
                communication: [
                    // avatar: 'https://picsum.photos/250/300?image=821'
                    {
                        title: 'Target US Data Status',
                        subtitle: 'More...',
                        value: '',
                        date: '4/2/2020',
                        time: '9:15:07 AM',
                        avatar: 'icons/target.png'
                    },
                    {
                        title: 'Target Data Status',
                        subtitle: 'More...',
                        value: '',
                        date: '4/2/2020',
                        time: '6:15:15 AM',
                        avatar: 'icons/target.png'
                    },
                    {
                        title: 'Calimax Data Status',
                        subtitle: 'More...',
                        value: '',
                        date: '4/2/2020',
                        time: '4:05:15 AM',
                        avatar: 'icons/calimax.jpg'
                    },
                    {
                        title: 'Sams CN SSC Data Status',
                        subtitle: 'More...',
                        value: '',
                        date: '4/2/2020',
                        time: '3:40:15 AM',
                        avatar: 'icons/sams.png',
                    },
                    {
                        title: 'Wallmart Category CN SSC Data Status -Resolved-',
                        subtitle: 'More...',
                        value: '',
                        date: '4/2/2020',
                        time: '3:10:15 AM',
                        avatar: 'icons/walmart.png'
                    },
                    {
                        title: 'Wallmart US Data Status -Resolved-',
                        subtitle: 'More...',
                        value: '',
                        date: '4/2/2020',
                        time: '2:25:16 AM',
                        avatar: 'icons/walmart.png'
                    }
                ]
            }
        }
    }
</script>

<style lang="scss">
    .first-page {
        //text-shadow: 3px 3px 9px rgba(0, 0, 0, 0.6);
        //box-shadow: 3px 3px 9px rgba(0, 0, 0, 0.3);

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

                p {
                    text-shadow: 3px 3px 11px rgba(0, 0, 0, 0.3);

                    .position-1 {
                        margin-left: -24px;
                    }

                    .position-2 {}

                    .position-3 {
                        margin-left: 24px;
                    }
                }
            }

            .card-style {
                box-shadow: 3px 3px 11px rgba(0, 0, 0, 0.3);
                //text-shadow: 3px 3px 9px rgba(0, 0, 0, 0.4);
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

    .first-page {
        .divider {
            margin-top: 150px;
        }
    }

    .first-page {
        .communication-section {
            //margin: auto;
            width: 90%;
            margin-left: 220px;
            margin-top: 90px;
            margin-bottom: 90px;

            .communication-title {
                position: absolute;
                left: 210px;
                font-size: 3.0rem !important;
                margin-top: 180px;
                font-weight: 300;
            }

            .communication-data {

                .communication-item {
                    width: 50%;
                    margin-left: 33% !important;

                    .list-data {
                        background: transparent;
                    }
                }
            }
        }
    }

</style>