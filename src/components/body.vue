<template>
    <div id="grid" :class="{otherView: grid}">
        <button @click="grid= !grid">Change View</button>
        <h3 v-for="tweet in tweets" v-bind:key="tweet"> {{ "Tweet Content: " + tweet.content + "  Posted By: " +  tweet.author + " Posted On: " + tweet.date  }} </h3>
    </div>
</template>

<script>
export default {
    name: "page-body",

    data: function(){
        return{
            tweets:[
                {
                    content: "This is a tweet",
                    author: "Bob",
                    date: "Feb 2 2020"
                },
                {
                    content: "This is a better tweet",
                    author: "Jill",
                    date: "Jan 12 2020"
                },
                {
                    content: "This is the best tweet",
                    author: "Judy",
                    date: "Aug 8 2020"
                },
                {
                    content: "This is a spooky tweet",
                    author: "Cam",
                    date: "Oct 31 2019"
                }
            ],
            grid: true,
        }
    }
}
</script>

<style scoped>
    #grid {
        display: grid;
        grid-template-rows: repeat(5, 1fr);
    }

    .otherView {
        display: grid;
        justify-items: center;
        align-items: center;
        grid-template-columns: repeat(5, 1fr);
    }

</style>