<template lang="pug">
    .contact-form
        .box
            b-input#inputSalt(
                placeholder="給我一點鹽"
            )
            b-button(
                type="is-primary"
            @click="recordSalt"
            ) 響指
        p#text 你好
</template>

<style lang="scss">
    .contact-form {
        width: 80%;

        .box {
            margin-top: 20px;
            
            #inputSalt {
                margin-bottom: 10px;
            }
        }
    }
</style>

<script>
    import Card from '~/components/Card'

    export default {
        name: 'HomePage',
        components: {
            Card
        },
        methods: {
            recordSalt(evt) {
                let helInputSalt = document.querySelector('#inputSalt');
                let helText = document.querySelector('#text');
                helText.innerHTML 
                    = helInputSalt.value
                    + '<br />'
                    + helText.innerHTML 
                ;
            },
        },
    }
</script>
