<template>
    <div class="pane">
        <ul class="list-group">
            <li class="list-group-header">
                {{ title }}
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        data () {
            return {
                title: 'Favorite Repos'
            };
        },
        methods: {
            getUserData () {
            }
        }
    };
</script>
