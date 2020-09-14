<template>
<v-app>
    <v-app-bar app dark prominent>
        <v-img src="../src/assets/mercadoulogo.png" max-width="50px">

        </v-img>
        <v-text class="amber--text subtitle">Painel de testes - API Mail</v-text>
    </v-app-bar>

    <v-main>
        <Sender />
    </v-main>
</v-app>
</template>

<script>
import Sender from './components/Sender'

export default {
    name: 'App',

    components: {
        Sender
    },

    data: () => ({
        //
    }),
};
</script>
