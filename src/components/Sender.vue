<template>
<div>
    <v-form color="primary">

    </v-form>
    <v-btn v-model="callAPI" @click="callAPI">Chamada da API</v-btn>
</div>
</template>

<script>
export default {
    name: 'Sender',

    methods: {

        callAPI() {
            const url = new URL(
                "https://api-app.iporto.com.br/api/panel/addressbook/5016/contacts"
            );

            let params = {
                //,
            };
            Object.keys(params)
                .forEach(key => url.searchParams.append(key, params[key]));

            let headers = {
                "Content-Type": "application/json",
                "Accept": "application/json",
                "Authorization": "Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsImp0aSI6ImVkMTY1YjNjNjJjYTgyOWNlNzRlOGMzOThjYjY5YTgxMGUxYmY3MTA2NzY0MzdkMmIwZTMyZTU1YjM0NDc4ZGQ5ZThiMTU4MTI2NzY2NzQ3In0.eyJhdWQiOiIxIiwianRpIjoiZWQxNjViM2M2MmNhODI5Y2U3NGU4YzM5OGNiNjlhODEwZTFiZjcxMDY3NjQzN2QyYjBlMzJlNTViMzQ0NzhkZDllOGIxNTgxMjY3NjY3NDciLCJpYXQiOjE2MDAxMDU1NzcsIm5iZiI6MTYwMDEwNTU3NywiZXhwIjoxNjMxNjQxNTc3LCJzdWIiOiIxOTUyIiwic2NvcGVzIjpbXX0.uqi4TNsLaWHzfS8ysZNkv4afNgCuqXloxnMVQH0H1GQmRxgXsdwILSZ37ttNPn6vzbRk25gNtSbLnuxDd4oXVN94uMnBwrk-Fx4Pi8Q0rNrhmO47broTwEmJF4fSFCiRn7JcKt4GyoWeSDU-cnAZi2STKEA6Ag79EhB_0q3hwlmHuGQIKdoJVu30fM76IUWJtdqpksdDZJ9AX0_m08R0X15mA323E9L4HzER6jWOz00octsYgq4OkTWvWkKoWBYyOkLkjYgB4Pfb4NWwGjAIvVzXj1uAa14w8q8OGspibgUzgGTdqdYfn1hjBH0FCGCa38xqnRI2a0hTWmVeJK5uj2TBgDmIgmV7622ObNfe_TC0i4vRbFwip--1kNZv6F8s5RTXowHfMQXzW4_LjsIUPteNnQIyDSjckVvBbdk41TEfqr6AWK52XdiSpX5eqzrlsP8X7plq71IeZDtB35tc-IqUMgSCvwhfyul5ys5MEb_mP6i7YPxVU6JYCvz7pgbz_Qi8TU67XRRk4LdXh-m178gMp3j4em_QpeBpk6hc-jdIg0sh6nN_ARXjteUePnY_avdMjCh9hrxRQSkwMWUjJGLIt0b9-No8r6QkKlZkggN0ScQe3BLLKsLfnwMXh6k_o4B8ocdqxeYKFpBxXNMLmOTDrieXleeSivLL-D2P6vw"

            };

            fetch(url, {
                    method: "GET",
                    headers: headers,
                })
                .then(response => response.json())
                .then(json => console.log(json));

        }
    }

}
</script>
