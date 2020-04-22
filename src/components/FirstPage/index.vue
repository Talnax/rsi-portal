<template>
    <div class="first-page">
        <v-timeline class="centrium">
            <!--color="indigo"-->
            <v-timeline-item
                color="indigo"
                right>
                <template v-slot:opposite>
                    <span class="timeline-item-title indigo--text"><b class="indigo--text">K</b>nowledge Hub</span>
                </template>
                <v-card class="card-style">
                    <v-img
                        height="150"
                        :src="getImgUrl('imgs/knowledge-7.jpeg')"
                    ></v-img>
                    <v-container>
                        <v-row>
                            <v-col class="hidden-sm-and-down" md="2">
                                <v-icon size="33">mdi-account-multiple-outline</v-icon>
                            </v-col>
                            <v-col cols="12" md="10">
                                Scaevola imperdiet nec ut,
                                sed euismod convenire principes at.
                            </v-col>
                        </v-row>
                    </v-container>
                </v-card>
            </v-timeline-item>

            <v-timeline-item
                color="cyan"
                left>
                <template v-slot:opposite>
                    <span class="timeline-item-title cyan--text">
                        <b class="cyan--text">E</b>vents
                    </span>
                </template>
                <v-card class="card-style">
                    <v-img
                        height="150"
                        :src="getImgUrl('imgs/events-1.jpg')"
                    ></v-img>
                    <v-container>
                        <v-row>
                            <v-col class="hidden-sm-and-down" md="2">
                                <v-icon size="33">event_available</v-icon>
                            </v-col>
                            <v-col cols="12" md="10">
                                Scaevola imperdiet nec ut,
                                sed euismod convenire principes nobis iisque
                            </v-col>
                        </v-row>
                    </v-container>
                </v-card>
            </v-timeline-item>

            <v-timeline-item
                color="blue"
                right>
                <template v-slot:opposite>
                    <span class="timeline-item-title blue--text"><b class="blue--text">D</b>ata Availability</span>
                </template>
                <v-card class="card-style">
                    <v-img
                        height="150"
                        :src="getImgUrl('imgs/data-availability-3.jpg')"
                    ></v-img>
                    <v-container>
                        <v-row>
                            <v-col class="hidden-sm-and-down" md="2">
                                <v-icon size="33">storage</v-icon>
                            </v-col>
                            <v-col cols="12" md="10">
                                Imperdiet nec ut, euismod convenire,
                                sed euismod convenire principes at iisque.
                            </v-col>
                        </v-row>
                    </v-container>
                </v-card>
            </v-timeline-item>

        </v-timeline>

        <hr class="divider">

        <div class="communication-section">
            <div class="communication-title ">
                <!--<p class="cyan--text"><b class="black--text">C</b>ommunication</p>-->
                <!--<p class="cyan--text"><b>C</b>ommunication</p>-->
                <p class="cyan--text"><b>C</b>ommunication</p>
            </div>

            <br><br><br>

            <v-list class="list-data" two-line>
                <template v-for="(item, index) in communication">
                    <v-list-item
                        :key="item.title"
                        ripple
                        @click="onListCommunicationClick(item)">
                        <v-list-item-avatar>
                            <img v-if="item.avatar.includes('icons')"
                                 :src="getImgUrl(item.avatar)">
                            <img v-else :src='item.avatar' >
                        </v-list-item-avatar>
                        <v-list-item-content>
                            <v-list-item-title ><b>{{ item.title }}</b></v-list-item-title>
                            <!--<v-list-item-subtitle v-html="item.date"></v-list-item-subtitle>-->
                        </v-list-item-content>
                        <v-list-item-content>
                            <v-list-item-subtitle style="margin-left: 90px;">{{ item.date}}</v-list-item-subtitle>
                        </v-list-item-content>
                        <v-spacer></v-spacer>
                        <!--<span>{{item.date}}, {{item.time}}</span>-->
                        <v-chip style="margin-right: 90px;">More...</v-chip>
                        <span>{{item.time}}</span>
                    </v-list-item>
                    <v-divider  inset></v-divider>
                </template>
            </v-list>
        </div>

        <hr class="divider">

        <div class="showcase-section">
            <div class="showcase-title">
                <p class="blue--text"><b>S</b>howcase</p>
                <div class="showcase-subtitle">
                    <b>Upcoming Webinar: Retail Shelf Alerting 5/5/2022</b>
                </div>
                <div class="showcase-explanation">
                    An introduction webinar to review the use cases around Retail Shelf Alerting, <br>
                    and its effectiveness for suppliers and retailers across the industry. <br>
                </div>
                <!--:src="getImgUrl(item.avatar)"-->
                <img class="showcase-image" :src="getImgUrl('screen-shots/rsi-aris.png')" alt="">
            </div>
        </div>

        <communication-more-dialog
            v-if="show_more_dlg"
            :show_dlg="show_more_dlg"
            :item="show_more_item"
            v-on:onCloseCommunicationMoreDialog="onCloseCommunicationMoreDialog">
        </communication-more-dialog>

    </div>
</template>

<script>
    import loadImageMixin from "@/mixins/loadImageMixin";
    import CommunicationMoreDialog from "@/dialogs/communication-more-dialog"

    export default {
        name: "index",
        mixins: [loadImageMixin],
        components: {
            "communication-more-dialog": CommunicationMoreDialog
        },
        data() {
            return {
                headers: [],
                rows: [],

                show_more_dlg: false,
                show_more_item: null,

                /*
                desserts: [
                    {
                        id: 1,
                        name: 'Target US',
                        date: "4/2/2020",
                        time: "9:15:06 AM",
                        icon: " "
                    },
                    {
                        id: 2,
                        name: 'Target',
                        date: "4/2/2020",
                        time: "9:15:06 AM",
                        icon: " "
                    },
                    {
                        id: 3,
                        name: 'Calimax',
                        date: "4/2/2020",
                        time: "9:15:06 AM",
                        icon: " "
                    }
                ],
                */

                communication: [
                    // avatar: 'https://picsum.photos/250/300?image=821'
                    {
                        title: 'Target US Data Status',
                        subtitle: '4/2/2020',
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
        },
        mounted() {
        },
        methods: {
            onListCommunicationClick(item) {
                console.log('onListCommunicationClick(item): ', item );
                this.onShowCommunicationMoreDialog(item);
            },

            onShowCommunicationMoreDialog(item) {
                console.clear();
                console.log("onShowCommunicationMoreDialog(item): ", item );
                this.show_more_item = item;
                this.show_more_dlg = true;
            },

            onCloseCommunicationMoreDialog() {
                console.log("onCloseCommunicationMoreDialog()");
                this.show_more_item = null;
                this.show_more_dlg = false;
            },
        }
    }
</script>

<style lang="scss">
    .first-page {
        //text-shadow: 3px 3px 9px rgba(0, 0, 0, 0.6);
        //box-shadow: 3px 3px 9px rgba(0, 0, 0, 0.3);

        .centrium {
            margin: auto;
            width: 63%;
            //left: 240px;
            top: 60px;

            .main-title {
                position: absolute;
                top: 270px;
                left: -450px;
                white-space: normal;
                //font-size: 3.6rem !important;
                font-size: 2.7rem !important;

                p {
                    text-shadow: 3px 3px 11px rgba(0, 0, 0, 0.3);
                }

                .position1 {
                    margin-left: -24px;
                }

                .position2 {}

                .position3 {
                    margin-left: 24px;
                }
            }

            .card-style {
                box-shadow: 3px 3px 11px rgba(0, 0, 0, 0.3);
                //text-shadow: 3px 3px 9px rgba(0, 0, 0, 0.4);
            }
        }

        .centrium {
            .timeline-item-title {
                font-size: 2.7rem !important;
                font-weight: 300;
            }
        }

        .v-card__title {
            //padding: 9px 15px !important;
            padding: 6px 15px !important;
        }

        .v-timeline:before {
            position: absolute;
            top: 141px;
            height: 68% !important;
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
            margin-top: 90px;

            .communication-title {
                position: absolute;
                font-size: 3.6rem !important;
                font-weight: 300;
                left: 50%;
                transform: translate(-50%, -50%);
            }

            .list-data {
                width: 50%;
                background: transparent;
                margin-left: 24% !important;
                //margin: auto;
            }

            .communication-data {
                width: 60%;
                margin-left: 15% !important;

                .list-data {
                    background: transparent;
                }
            }
        }
    }

    .first-page {
        .showcase-section {
            margin-top: 30px;
            margin-bottom: 90px;

            .showcase-title {
                font-size: 3.6rem !important;
                font-weight: 300;
                text-align: center;
            }

            .showcase-subtitle {
                font-size: 1.8rem !important;
            }

            .showcase-explanation {
                margin-top: 15px;
                font-size: 18px;
            }

            .showcase-image {
                margin-top: 30px;
                width: 60%;

                background-position: center;
                background-repeat: no-repeat;
                background-size: cover;
            }

        }
    }

    /*
    .first-page {
        .communication-section {
            .communication-table {

                .dimension_measure-table {
                    width: 40%;
                    margin: auto;
                    background-color: transparent !important;

                    .table-header {
                        background-color: transparent !important;
                    }
                }
            }
        }
    }
    */

</style>