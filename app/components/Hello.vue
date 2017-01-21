<template>
    <div class="hello">
        <h1>{{ msg }}</h1>
        <button v-on:click="getPatrickData()">Get Patrick Data</button>
    </div>
</template>

<script>
    import { remote } from 'electron';
    import os from 'os';
    import GitHub from 'github-api';
    export default {
        data () {
            return {
                platform: os.platform(),
                appName: remote.app.getName(),
                // note: changing this line won't causes changes
                // with hot-reload because the reloaded component
                // preserves its current state and we are modifying
                // its initial state.
                msg: 'GitWorkHubFlow'
            };
        },
        methods: {
            getPatrickData () {
                const gh = new GitHub();
                const pdsullivan = gh.getUser('pdsullivan');
                pdsullivan.getProfile()
                    .then(({data: userData}) => {
                        this.msg = `Hello ${userData.name}!`;
                    });
            }
        }
    };
</script>
