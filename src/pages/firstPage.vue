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

                        <v-card v-for="item in list.list">
                            
                            <v-card-text :href="item.url" class="grey lighten-3">{{ item.name}}</v-card-text>
                            <!-- 
                            <a :href="item.url" class="grey lighten-3">{{ item.name}}</a>
 -->
                        </v-card>                        
                    </v-expansion-panel-content>
                </v-expansion-panel>                
            </v-list>
        </v-navigation-drawer>
        <v-toolbar fixed class="indigo darken-4" dark>
            <v-toolbar-side-icon @click.native.stop="drawer = !drawer"></v-toolbar-side-icon>
            <v-toolbar-title>Toolbar</v-toolbar-title>
        </v-toolbar>
        <main>
            <v-container fluid>
                <div class="title">Click on sidebar to re-open.</div>
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
            items: [
                { title: 'Home', icon: 'dashboard' },
                { title: 'About', icon: 'question_answer' }
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