<template>
    <v-navigation-drawer expand-on-hover rail permanent theme="dark">
        <v-list>
            <v-list-item
                prepend-avatar="https://avatars.githubusercontent.com/u/82406773?s=400&u=5cb63d44a35c0d41371d205f3c6f135aeef3e07b&v=4"
                title="Joscelyn Covarrubias" subtitle="joscelyn.covarrubias@uabc.edu.mx">
            </v-list-item>
        </v-list>

        <v-divider></v-divider>

        <v-list density="compact" nav>
            <v-list-item prepend-icon="mdi-home-flood" title="Home" value="home" to="/"></v-list-item>
            <v-list-item prepend-icon="mdi-table" title="Table" value="table" to="/tabla"></v-list-item>
            <v-list-item prepend-icon="mdi-bookmark" title="" value="hola"></v-list-item>
        </v-list>

    </v-navigation-drawer>
</template>