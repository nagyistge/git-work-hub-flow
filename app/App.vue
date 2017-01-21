<template>
    <div id="app" class="window">
        <div class="window-content">
            <div class="pane-group">
                <side-bar></side-bar>
                <your-repositories></your-repositories>
                <favorite-repos></favorite-repos>
                <reviews-requested></reviews-requested>
            </div>
        </div>
    </div>
</template>

<script>
    import FavoriteRepos from './components/FavoriteRepos';
    import SideBar from './components/SideBar';
    import ReviewsRequested from './components/ReviewsRequested';
    import YourRepositories from './components/YourRepositories';
    export default {
        components: {
            SideBar,
            FavoriteRepos,
            ReviewsRequested,
            YourRepositories
        }
    };
</script>

<style>
    .pane .list-group {
        margin-top: 55px;
    }
    .pane .list-group .list-group-header {
        position: fixed;
        /*width: 100%;*/
        background-color: white;
        top: 0;
    }
</style>
