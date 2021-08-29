<template>
    <div>

        <v-container>

        <v-data-table
            dense
            v-model="selected"
            :headers="headers"
            :items="desserts"
            :single-select="true"
            :light="true"
            item-key="horse_no"
            sort-desc
            :fixed-header="true"
            :height="360"
            :mobile-breakpoint="300"
            hide-default-footer
            class="elevation-1"
        >
        
        <template v-slot:item="props">
            <tr>
                <!-- チェックボックス -->
                <td>
                    <v-checkbox 
                        color="blue-grey darken-2" 
                        v-model="checkbox" 
                        :value="props.item.horse_no"
                    ></v-checkbox>
                </td>
                
                <!-- 枠番 -->
                <td class="text-xs-right pa-0">
                    <v-chip label :color="getColorWakuBan(props.item.waku_no)">
                        {{ props.item.waku_no }}
                    </v-chip>
                </td>

                <!-- 馬番 -->
                <td class="text-xs-right pa-0">
                    <v-chip label :color="getColorUmaBan(props.item.horse_no)">
                        {{ props.item.horse_no }}
                    </v-chip>
                </td>

                <!-- 馬名 -->
                <td class="text-xs-right pa-3">
                    <div 
                        class="d-inline-block text-truncate font-weight-black black--text" 
                        style="max-width:120px;"
                    >
                        {{ props.item.horse_name }}
                    </div>
                </td>
                
                <!-- オッズ -->
                <td class="text-xs-right pa-0">
                    <div :class="getColorOdds(props.item.odds)">
                        {{ props.item.odds }}
                    </div>
                </td>
            </tr>
        </template>  
        
        </v-data-table>


        </v-container>

        <v-container>
            <div class="text-center">
                <!-- <v-btn outlined rounded>Create Text</v-btn> -->
                <!-- <v-btn outlined rounded>Create Text</v-btn> -->
                <v-btn outlined rounded>Create URL</v-btn>
            </div>
        </v-container>

    </div>
</template>

<script>
export default {
    data() {
        return {
            checkbox: false,
            selected: [],
            headers: [
            { text: '印', value: 'checkbox'},
            {
                // text: 'Dessert (100g serving)',
                text: '枠',
                align: 'start',
                sortable: false,
                class: 'px-0',
                value: 'waku_no',
            },
            { text: '番', class: 'px-0', value: 'horse_no' },
            { text: '馬名', class: 'px-0', value: 'horse_name' },
            { text: 'オッズ', class: 'px-0', value: 'odds' },
            ],
            desserts: [
            {
                waku_no: '1',
                horse_no: 1,
                horse_name: 'ハーツクライ',
                odds: 3.5,
            },
            {
                waku_no: '2',
                horse_no: 2,
                horse_name: 'ネロ',
                odds: 6.7,
            },
            {
                waku_no: '3',
                horse_no: 3,
                horse_name: 'クリノスターオー',
                odds: 13.8,
            },
            {
                waku_no: '4',
                horse_no: 4,
                horse_name: 'エキマエ',
                odds: 20.1,
            },
            {
                waku_no: '5',
                horse_no: 6,
                horse_name: 'サヴィ',
                odds: 30.7,
            },
            ]
        }
    },
    methods: {
        getColorWakuBan (event) {
            if (event == 1) return 'grey lighten-4'
            else if (event == 2) return 'grey darken-4 white--text'
            else if (event == 3) return 'red lighten-1 white--text'
            else if (event == 4) return 'blue darken-3 white--text'
            else return 'green darken-2 white--text'
        },
        getColorUmaBan (event) {
            if (event == 1) return 'grey lighten-4'
            else if (event == 2) return 'grey darken-4 white--text'
            else if (event == 3) return 'red lighten-1 white--text'
            else if (event == 4) return 'blue darken-3 white--text'
            else return 'green darken-2 white--text'
        },
        getColorOdds (event) {
            if (event <= 5.0) return 'red--text font-weight-medium'
            else if (event <= 10.0) return 'orange--text font-weight-medium'
            else if (event <= 15.0) return 'black--text font-weight-medium'
            else return 'black--text'
        },
    },
}
</script>
