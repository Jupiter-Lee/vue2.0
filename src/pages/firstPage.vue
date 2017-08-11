<template>
    <v-app id="example-2" standalone>
        <v-navigation-drawer absolute persistent light :mini-variant.sync="mini" v-model="drawer" overflow>
            <v-toolbar flat class="transparent">
                <v-list class="pa-0">
                    <v-list-tile avatar tag="div">
                        <v-list-tile-avatar>
                            <img src="https://randomuser.me/api/portraits/men/85.jpg" />
                        </v-list-tile-avatar>
                        <v-list-tile-content>
                            <v-list-tile-title>John Leider</v-list-tile-title>
                        </v-list-tile-content>
                        <v-list-tile-action>
                            <v-btn icon @click.native.stop="mini = !mini">
                                <v-icon>chevron_left</v-icon>
                            </v-btn>
                        </v-list-tile-action>
                    </v-list-tile>
                </v-list>
            </v-toolbar>
            <v-list class="pt-0" dense>
                <v-divider></v-divider>
                <v-expansion-panel>
                    <v-expansion-panel-content v-for="list in sideList">
                        <div slot="header">{{ list.title }}</div>
                        <div class="index-left-block">
                            <ul>
                                <li v-for="item in list.list">
                                    <a :href="item.url" class="grey lighten-3">{{ item.name}}</a>
                                </li>
                            </ul>
                        </div>
                        <!-- 
                                <v-card v-for="item in list.list">
                                    
                                    <v-card-text :href="item.url" class="grey lighten-3">{{ item.name}}</v-card-text>
                                </v-card>   
                                  -->
                    </v-expansion-panel-content>
                </v-expansion-panel>
            </v-list>
        </v-navigation-drawer>
        <v-toolbar fixed class="indigo darken-4" dark>
            <v-toolbar-side-icon @click.native.stop="drawer = !drawer"></v-toolbar-side-icon>
            <v-toolbar-title>杭州能联科技有限公司</v-toolbar-title>
        </v-toolbar>
        <main>
            <v-container fluid>
                <!-- <div class="title">Click on sidebar to re-open.</div> -->
                <template>
                    <v-data-table v-bind:headers="headers" :items="items" hide-actions class="elevation-1">
                        <template slot="items" scope="props">
                            <td>{{ props.item.name }}</td>
                            <td class="text-xs-right">{{ props.item.calories }}</td>
                            <td class="text-xs-right">{{ props.item.fat }}</td>
                            <td class="text-xs-right">{{ props.item.carbs }}</td>
                            <td class="text-xs-right">{{ props.item.protein }}</td>
                            <td class="text-xs-right">{{ props.item.sodium }}</td>
                            <td class="text-xs-right">{{ props.item.calcium }}</td>
                            <td class="text-xs-right">{{ props.item.iron }}</td>
                        </template>
                    </v-data-table>
                </template>
                <!--v-router-->
                
            </v-container>
        </main>
    </v-app>
</template>

<script>
export default {
    data() {
        return {
            drawer: true,
            headers: [
                {
                    text: 'Dessert (100g serving)',
                    align: 'left',
                    sortable: false,
                    value: 'name'
                },
                { text: 'Calories', value: 'calories' },
                { text: 'Fat (g)', value: 'fat' },
                { text: 'Carbs (g)', value: 'carbs' },
                { text: 'Protein (g)', value: 'protein' },
                { text: 'Sodium (mg)', value: 'sodium' },
                { text: 'Calcium (%)', value: 'calcium' },
                { text: 'Iron (%)', value: 'iron' }
            ],
            items: [
                {
                    value: false,
                    name: 'Frozen Yogurt',
                    calories: 159,
                    fat: 6.0,
                    carbs: 24,
                    protein: 4.0,
                    sodium: 87,
                    calcium: '14%',
                    iron: '1%'
                },
                {
                    value: false,
                    name: 'Ice cream sandwich',
                    calories: 237,
                    fat: 9.0,
                    carbs: 37,
                    protein: 4.3,
                    sodium: 129,
                    calcium: '8%',
                    iron: '1%'
                },
                {
                    value: false,
                    name: 'Eclair',
                    calories: 262,
                    fat: 16.0,
                    carbs: 23,
                    protein: 6.0,
                    sodium: 337,
                    calcium: '6%',
                    iron: '7%'
                },
                {
                    value: false,
                    name: 'Cupcake',
                    calories: 305,
                    fat: 3.7,
                    carbs: 67,
                    protein: 4.3,
                    sodium: 413,
                    calcium: '3%',
                    iron: '8%'
                },
                {
                    value: false,
                    name: 'Gingerbread',
                    calories: 356,
                    fat: 16.0,
                    carbs: 49,
                    protein: 3.9,
                    sodium: 327,
                    calcium: '7%',
                    iron: '16%'
                },
                {
                    value: false,
                    name: 'Jelly bean',
                    calories: 375,
                    fat: 0.0,
                    carbs: 94,
                    protein: 0.0,
                    sodium: 50,
                    calcium: '0%',
                    iron: '0%'
                },
                {
                    value: false,
                    name: 'Lollipop',
                    calories: 392,
                    fat: 0.2,
                    carbs: 98,
                    protein: 0,
                    sodium: 38,
                    calcium: '0%',
                    iron: '2%'
                },
                {
                    value: false,
                    name: 'Honeycomb',
                    calories: 408,
                    fat: 3.2,
                    carbs: 87,
                    protein: 6.5,
                    sodium: 562,
                    calcium: '0%',
                    iron: '45%'
                },
                {
                    value: false,
                    name: 'Donut',
                    calories: 452,
                    fat: 25.0,
                    carbs: 51,
                    protein: 4.9,
                    sodium: 326,
                    calcium: '2%',
                    iron: '22%'
                },
                {
                    value: false,
                    name: 'KitKat',
                    calories: 518,
                    fat: 26.0,
                    carbs: 65,
                    protein: 7,
                    sodium: 54,
                    calcium: '12%',
                    iron: '6%'
                }
            ],
            sideList: {
                archiveMana: {
                    title: '档案管理',
                    list: [
                        {
                            name: '区域信息',
                            url: ''
                        },
                        {
                            name: '建筑物信息',
                            url: ''
                        },
                        {
                            name: '房间信息',
                            url: ''
                        },
                        {
                            name: '表计信息',
                            url: 'orderList'
                        }
                    ]
                },
                meterMana: {
                    title: '抄表管理',
                    list: [
                        {
                            name: '户表监控',
                            url: ''
                        },
                        {
                            name: '实时抄表',
                            url: ''
                        },
                        {
                            name: '数据补抄',
                            url: ''
                        }
                    ]
                },
                maintainMana: {
                    title: '运行维护',
                    list: [
                        {
                            name: '集中器管理',
                            url: ''
                        },
                        {
                            name: '采集器管理',
                            url: ''
                        },
                        {
                            name: '路由操作',
                            url: ''
                        }
                    ]
                }
            },
            mini: false,
            right: null
        }
    }
}
</script>

<<style>
.index-left-block {
  background: #fff;
  box-shadow: 0 0 1px #ddd;
}

.index-left-block .hr {
  margin-bottom: 20px;
}

.index-left-block h2 {
  background: #4fc08d;
  color: #fff;
  padding: 10px 15px;
  margin-bottom: 20px;
}

.index-left-block h3 {
  padding: 0 15px 5px 15px;
  font-weight: bold;
  color: #222;
}

.index-left-block ul {
  padding: 10px 15px;
}

.index-left-block li {
  padding: 5px;
}
</style>
