<script>
import axios from 'axios'
import Swal from 'sweetalert2'
import { Form, Field, ErrorMessage} from 'vee-validate'

export default {
    components: {
        Form,
        Field,
        ErrorMessage
    },
    data() {
        return {
            form: {
                name: '',
                lastname: '',
                email: '',
                phone: ''
            },
            isDisabledButton: false,
            isDisabledInput: false
        }
    },
    methods: {
        sendData(e) {
            this.isDisabledButton = true;
            this.isDisabledInput = true;

            axios.post('https://5eed24da4cbc340016330f0d.mockapi.io/api/newsletter', this.form)
              .then(response => {
                    Swal.fire({
                        icon:'success',
                        title: 'Data send successfully',
                        showConfirmButton: false,
                        timer: 1500
                    })

                    this.isDisabledButton = false;
                    this.isDisabledInput = false;
                })
              .catch(error => {
                    Swal.fire({
                        icon: 'error',
                        title: 'An error occurred',
                        showConfirmButton: false,
                        timer: 1500
                    })
                })
        },

        validName(value) {
            if (!value) {
                return 'Este campo es requerido';   
            }

            return true;
        },
        validLastname(value) {
            if (!value) {
                return 'Este campo es requerido';   
            }

            return true;
        },
        validEmail(value) {
            if (!value) {
                return 'Este campo es requerido';   
            }

            const emailRegex = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;

            if (!emailRegex.test(value)) {
                return 'Debe ingresar un email válido';
            }

            return true;
        },
        validPhone(value) {
            if (!value) {
                return 'Este campo es requerido';   
            }

            if (isNaN(value)) {
                return 'El teléfono solo debe contener dígitos';
            }

            if (value.length < 8 || value.length > 14) {
                return 'El teléfono debe contener entre 8 y 14 dígitos';
            }

            return true;
        }
    }
}

</script>

<template>
    <h2 class="contactform__title">Contáctanos</h2>
    <Form action="" @submit="sendData" class="contactform__content" v-slot="{ errors }">
        <div class="contactform__inputs-container">
            <div>
                <label for="name" class="contactform__input-label">Nombre</label>
                <Field type="text" name="name" class="contactform__input" :class="{ 'error__input': errors.name }" v-model="form.name" :rules="validName"/>
                <span class="contactform__error">
                    <ErrorMessage name="name" />
                </span>
            </div>
            <div>
                <label for="lastname" class="contactform__input-label">Apellido</label>
                <Field type="text" name="lastname" class="contactform__input" :class="{ 'error__input': errors.lastname }" v-model="form.lastname" :rules="validLastname"/>
                <span class="contactform__error">
                    <ErrorMessage name="lastname" />
                </span>
            </div>
            <div>
                <label for="email" class="contactform__input-label">Mail</label>
                <Field type="email" name="email" class="contactform__input" :class="{ 'error__input': errors.email }" v-model="form.mail" :rules="validEmail"/>
                <span class="contactform__error">
                    <ErrorMessage name="email" />
                </span>
            </div>
            <div>
                <label for="phone" class="contactform__input-label">Téléfono</label>
                <Field type="tel" name="phone" class="contactform__input" v-model="form.phone" :class="{ 'error__input': errors.phone }" :rules="validPhone"/>
                <span class="contactform__error">
                    <ErrorMessage name="phone" />
                </span>
            </div>
        </div>

        <input type="submit" :disabled="isDisabledButton || errors.name || errors.lastname || errors.email || errors.phone" class="contactform__submit" value="Enviar">
    </Form>
</template>