<template>
    <v-container>
        <v-row justify="space-around">
            <v-card width="600">
                <v-img height="350" :src="url" cover class="text-white">
                    <v-toolbar color="rgba(0, 0, 0, 0)" theme="dark">
                        <v-toolbar-title class="text-h6">
                            Desarrollo de Aplicaciones WEB
                        </v-toolbar-title>

                        <template v-slot:append>
                            <v-btn icon="mdi-refresh" @click="messages = []"></v-btn>
                        </template>
                    </v-toolbar>
                </v-img>

                <v-card-text>
                    <div class="font-weight-bold ms-1 mb-2">
                        Today
                    </div>

                    <v-timeline density="compact" align="start">
                        <v-timeline-item v-for="message in messages" :key="message.time" :dot-color="message.color"
                            size="x-small">
                            <div class="mb-4">
                                <div class="font-weight-normal">
                                    <strong>{{ message.from }}</strong> @{{ message.time }}
                                </div>
                                <div>{{ message.message }}</div>
                            </div>
                        </v-timeline-item>
                    </v-timeline>
                </v-card-text>
                <v-card-actions>
                    <v-btn @click="recargaImagen" :color="red">
                        Reload
                    </v-btn>
                </v-card-actions>
            </v-card>
        </v-row>
    </v-container>
</template>

<script setup>

import { ref } from 'vue';
const messages = ref([]);
const red = ref("blue");
const url = ref("https://picsum.photos/650/350/?blur=1");

messages.value = [

    {
        from: 'Joscelyn',
        message: `Sure, I'll see you later.`,
        time: '10:42am',
        color: 'deep-purple-lighten-1',
    },
    {
        from: 'You',
        message: 'Did you still want to grab lunch today?',
        time: '9:47am',
        color: 'deep-purple-lighten-1',
    },
];
async function recargaImagen() {

    let r = await fetch("https://picsum.photos/650/350/?blur=1");
    url.value = r.url;
    console.log(url.value);

    if (red.value == "blue") {
        red.value = "red";
    } else {
        red.value = "blue";
    }
    console.log("recargando Imagen..");

}
</script>




