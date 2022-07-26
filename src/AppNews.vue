<template>

    <div class="card">
        <h2 class="text-text">{{ id }} {{ title }}</h2>
        <button class="btn" @click="open">
            {{ isNewsOpen ? "Close" : "Open" }}
        </button>
        <!-- <button class="btn" @click="open">Close</button> -->
        <diV v-if="isNewsOpen">
            <hr />

            <p class="title">Lorem ipsum dolor sit amet consectetur adipisicing elit. Magni laudantium
                voluptates earum,
                quisquam non odit accusamus nemo. Deleniti, odio nisi, placeat exercitationem saepe eligendi pariatur
                delectus reprehenderit velit eaque soluta?</p>
            <button v-if="!wasRead" class="btn primary" @click="mark">Read the news</button>
        </diV>

    </div>


</template>


<script>
export default {
    // props: ["title"],
    props: {
        title: String,
        id: Number,
        isOpen: Boolean,
        wasRead: Boolean
    },
    data() {
        return {
            isNewsOpen: this.isOpen
        }
    },
    methods: {
        open() {
            this.isNewsOpen = !this.isNewsOpen
            if (this.isNewsOpen) {
                this.$emit("open-news")
            }

        },
        mark() {
            this.isNewsOpen = false
            this.$emit("read-news", this.id)
        }

    }
}

</script>