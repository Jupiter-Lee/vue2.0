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
                <v-list-tile v-for="item in items" :key="item.title">
                    <v-list-tile-action>
                        <v-icon>{{ item.icon }}</v-icon>
                    </v-list-tile-action>
                    <v-list-tile-content>
                        <v-list-tile-title>{{ item.title }}</v-list-tile-title>
                    </v-list-tile-content>
                </v-list-tile>
                <v-expansion-panel>
                    <v-expansion-panel-content v-for="(item,i) in 5" :key="i">
                        <div slot="header">Item</div>
                        <v-card>
                            <v-card-text class="grey lighten-3">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</v-card-text>
                        </v-card>
                    </v-expansion-panel-content>
                </v-expansion-panel>
                <v-expansion-panel>
                    <v-expansion-panel-content v-for="archive in archiveList">
                        <div slot="header">档案管理</div>
                        <v-card>
                            <v-card-text class="grey lighten-3">{{ archive.title}}</v-card-text>
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
            archiveList: {
                area: {
                    title: '区域管理',
                    url: ''
                },
                concentrator: {
                    title: '集中器管理',
                    url: ''
                }
            },
            mini: false,
            right: null
        }
    }
}
</script>