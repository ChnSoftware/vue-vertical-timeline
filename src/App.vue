<template>
    <Timeline
        v-for="(note, index) in notes"
        :key="note.id"
        :note="note"
        :index="index"
        :length="notes.length"
    />
</template>

<script>
    import Timeline from "@/components/Timeline"

    export default {
        name: 'App',
        components: { Timeline },
        data() {
            return {
                notes: [
                    {
                        title: "dcode",
                        paragraph: "My fist YouTube video was a tutorial on how to build a client-server socket app in Java.",
                        date: "July, 23 2021"
                    },
                    {
                        title: "Arin Yazılım",
                        paragraph: "My fist YouTube video was a tutorial on how to build a client-server socket app in Java.",
                        date: "July, 23 2021"
                    },
                    {
                        title: "kablosuzkedi",
                        paragraph: "My fist YouTube video was a tutorial on how to build a client-server socket app in Java.",
                        date: "July, 23 2021"
                    },
                    {
                        title: "Adem İlter",
                        paragraph: "My fist YouTube video was a tutorial on how to build a client-server socket app in Java.",
                        date: "July, 23 2021"
                    },
                    {
                        title: "Prototürk",
                        paragraph: "My fist YouTube video was a tutorial on how to build a client-server socket app in Java.",
                        date: "July, 23 2021"
                    },
                    {
                        title: "Vue Turkey",
                        paragraph: "My fist YouTube video was a tutorial on how to build a client-server socket app in Java.",
                        date: "July, 23 2021"
                    },
                ]
            }
        }
    }
</script>

<style lang="scss">
    @import url("https://fonts.googleapis.com/css2?family=Fira+Sans:wght@400;500;700&display=swap");

    * {
        padding: 0;
        margin: 0;
        list-style: none;
        border: none;
        text-decoration: none;
        box-sizing: border-box;
        -webkit-overflow-scrolling: touch;
        font-family: "Fira Sans", sans-serif;

        &:focus {
            outline: 0;
        }
    }
    body {
        background-color: #009578;
        padding: 25px;
    }
</style>
