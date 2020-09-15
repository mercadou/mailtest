<template>
<div>
    <v-form color="primary">

    </v-form>
    <v-btn v-model="callAPI" @click="callAPI">Puxar Listas</v-btn>
    <v-btn v-model="callAPI" @click="callAPI">Puxar Contatos da Lista 1</v-btn>
</div>
</template>

<script>
export default {
    name: 'Sender',

    methods: {

        callAPI() {
            const url = new URL(
                "https://api-app.iporto.com.br/api/panel/smtp/1/account/1/email/send/test"
            );

            let params = {
                "domain": "1617",
                "account": "2204",
            };
            Object.keys(params)
                .forEach(key => url.searchParams.append(key, params[key]));

            let headers = {
                "Content-Type": "application/json",
                "Accept": "application/json",
                "Authorization": "Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsImp0aSI6ImQ5YzQwNTNmNmYxMTMwNzM0M2RmYjI2N2E0NjRiMGZlNGNmMmQwMWM4YTBjMjM3MjIzYmUwMGYxZjk4NjgxM2NmOWMwNTU1ZGY2NDY0OTE5In0.eyJhdWQiOiIxIiwianRpIjoiZDljNDA1M2Y2ZjExMzA3MzQzZGZiMjY3YTQ2NGIwZmU0Y2YyZDAxYzhhMGMyMzcyMjNiZTAwZjFmOTg2ODEzY2Y5YzA1NTVkZjY0NjQ5MTkiLCJpYXQiOjE2MDAxNzk4MjUsIm5iZiI6MTYwMDE3OTgyNSwiZXhwIjoxNjMxNzE1ODI1LCJzdWIiOiIxOTQyIiwic2NvcGVzIjpbXX0.PRLWPbEOoXe6Al6nm2u_DY7uM03wxG1V2Efe36dlZJvL_izlszSIhzNQWCuDmbktoPP7cY5CLcZzbwtYmZ3wVwyznk6W1Ll-Qf5vNFFqHY09gymv88aQ2nX3RAKy_kcmXuo4PzxqJ7mdHA14cJZiAaU8bHCKZz0pqvUa6ftorBaY7TQXf1V5vQifhuiUPRQaeu438lF89mHvObBcfkOjDIsJulePtnNxxfOuh5_27L4Jvu86zgCUji5DvSt9C25IJ6FXX6kWkhVqLw8mkWW5Ga2UG1-CHbSMSb2GQGKcuFXjMkK6PwSo5BlLm7Bar3YHn6cW6J1yyqYtBvaYX9RK2c5t3qeNcF8DoXXKBu5Qy6knIcdbTlqgN9zfwZ-gs6Lg0H5XYUWamuTahGuMrgs7Q2kuw7QzBaqfOLCEFdxbN5viIriKxe-PUA9RTH29KiIawm6TWylYlcCKdMtq4krOwFJZJw0bbwiXjb7TIiUn03xYcXepF3Gy0u_X9M5MbI_DhySZaPcXUVdCPgBXNdU_EwLyk3ajBBsNfQuVpD3q4v1Dl8MB9aNe-8owaj8N7VE_stVacEN-TR7XeRLd7Q_PmLC03DBwbRrGF0J7HIoa5GhJph5c1E04OmHhAT_XrqKhSsYIIYqzWg_8kNoFIeii34Gu6jmnliygx43oYOmjdbc"

            };

            fetch(url, {
                    method: "POST",
                    headers: headers,
                })
                .then(response => response.json())
                .then(json => console.log(json));

        }
    }

}
</script>
