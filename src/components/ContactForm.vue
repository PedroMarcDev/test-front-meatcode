<script>
import axios from 'axios'
import Swal from 'sweetalert2'

export default {
    data() {
        return {

        }
    },
    methods: {
    }
}

</script>

<template>
    <h2 class="contactform__title">Contáctanos</h2>
    <form action="" class="contactform__content">
        <div class="contactform__inputs-container">
            <div>
                <label for="name" class="contactform__input-label">Nombre</label>
                <input type="text" name="name" class="contactform__input">
            </div>
            <div>
                <label for="lastname" class="contactform__input-label">Apellido</label>
                <input type="text" name="lastname" class="contactform__input">
            </div>
            <div>
                <label for="email" class="contactform__input-label">Mail</label>
                <input type="email" name="email" class="contactform__input">
            </div>
            <div>
                <label for="phone" class="contactform__input-label">Téléfono</label>
                <input type="tel" name="phone" class="contactform__input">
            </div>
        </div>

        <input type="submit" class="contactform__submit" value="Enviar">
    </form>
</template>