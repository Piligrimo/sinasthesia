<template>
    <span :style="{color: color}">{{character}}</span>
</template>

<script>
const dictionary = {
    "0": "#efebe7",
    "1": "#dedbde",
    "2": "#6b2821",
    "3": "#d69608",
    "4": "#10b6ce",
    "5": "#b53473",
    "6": "#215900",
    "7": "#5ab629",
    "8": "#ad1c6b",
    "9": "#000000",
    ",": "#000000",
    ".": "#000000",
}

export default {
    props: {
        character: String
    },
    computed: {
        color () {
            return dictionary[this.character]
        }
    }
}
</script>

<style>
span {
font-weight: bold;
font-size: 4rem;
word-break: break-all;
text-shadow: 1px 1px 1px #000;

}
</style>