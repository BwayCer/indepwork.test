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
      p#text 我好
      p#text.button.is-primary.is-medium(
        @click="isComponentModalActive = true"
      ) 你好
      b-modal(
        :active.sync='isComponentModalActive',
        b-has-modal-card=''
      )
        modal-form(v-bind='formProps')
        | 他好
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

    const ModalForm = {
        props: ['email', 'password'],
        template: `<div>{{email}}: {{password}}</div>`
    }

    export default {
        name: 'FiatDeposit',
        components: {
            Card,
            ModalForm
        },
        data() {
            return {
                isComponentModalActive: false,
                formProps: {
                    email: 'evan@you.com',
                    password: 'testing'
                }
            }
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
