<template>
    <div class="timeline" :class="reverse">
        <div class="timeline__component item--1">
            <div class="timeline__date" :class="right">
                {{ note.date }}
            </div>
        </div>
        <div class="timeline__middle item--2">
            <div class="timeline__point"></div>
            <div
                v-if="length === index + 1"
                class="timeline__point timeline__point--bottom"
            ></div>
        </div>
        <div class="timeline__component  timeline__component--bg item--3" :class="bottomMargin">
            <h2 class="timeline__title">{{ note.title }}</h2>
            <p class="timeline__paragraph">
                {{ note.paragraph }}
            </p>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Timeline",
        props: {
            note: {
                type: Object,
                required: true
            },
            index: {
                type: Number
            },
            length: {
                type: Number
            }
        },
        computed: {
            reverse() {
                return {
                    "reverse": this.index % 2 === 1
                }
            },
            right() {
                return {
                    "timeline__date--right": this.index % 2 === 0
                }
            },
            bottomMargin(){
                return{
                    "timeline__component--bottom": this.length === this.index + 1
                }
            }
        }
    }
</script>

<style lang="scss">
    .timeline {
        max-width: 750px;
        margin: 0 auto;
        display: grid;
        grid-template-columns: 1fr 3px 1fr;
        grid-template-areas: "item1 item2 item3";
        color: white;

        &.reverse {
            grid-template-areas: "item3 item2 item1";
        }
        .item--1 {
            grid-area: item1;
        }
        .item--2 {
            grid-area: item2;
        }
        .item--3 {
            grid-area: item3;
        }

        &__component {
            margin: 0 20px 20px 20px;

             &--bottom{
            margin-bottom: 0;
            }

            &--bg {
                padding: 1.5em;
                background-color: rgba(255, 255, 255, 0.2);
                border-radius: 10px;
                box-shadow: 0 0 5px rgba(0, 0, 0, 0.2);
            }
            .timeline__title {
                font-size: 1.15em;
            }
            .timeline__paragraph {
                margin: 1em 0;
                line-height: 1.5;
            }
        }
        &__date {
            &--right {
                text-align: right;
            }
        }
        &__middle {
            background: white;
            position: relative;
        }
        &__point {
            position: absolute;
            top: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 15px;
            height: 15px;
            background-color: white;
            border-radius: 50%;

            &--bottom {
                top: initial;
                bottom: 0;
            }
        }
    }
</style>