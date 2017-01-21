<template>
    <div class="pane">
        <ul class="list-group">
          <li class="list-group-header">
            <input class="form-control" v-model="userName" type="text" placeholder="Github Username">
          </li>
          <li class="list-group-item">
              <button class="btn btn-default" v-on:click="getUserData()">
                  Get Repos
              </button>
          </li>
          <li class="list-group-item" v-for="repo in repos">
            <div class="media-body">
              <strong>{{repo.full_name}}</strong>
              <p>{{repo.description}}</p>
            </div>
          </li>
        </ul>
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
                msg: 'GitWorkHubFlow!',
                userData: null,
                repos: null,
                userName: null
            };
        },
        methods: {
            getUserData () {
                const gh = new GitHub();
                const pdsullivan = gh.getUser(this.userName);
                pdsullivan.getProfile()
                    .then(({data: userData}) => {
                        this.userData = userData;
                    });
                pdsullivan.listRepos()
                    .then(({data: repos}) => {
                        this.repos = repos;
                    });
            }
        }
    };
</script>
