<template>
    <div class="hello">
        <h1>{{ title }}</h1>
        <p>
            This will be a list of your repositories (or a search box filter or something)....
        </p>
    </div>
</template>

<script>
    export default {
        data () {
            return {
                title: 'Your Repositories'
            };
        },
        methods () {
            return {
                getData () {
                }
            };
        }
    };
</script>
