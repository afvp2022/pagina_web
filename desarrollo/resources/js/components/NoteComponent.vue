<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8">
                <form action="" @submit.prevent="newNote">
                    <div class="card">
                        <div class="card-header">Generar Notas</div>
                        <div class="card-body">
                            <input type="text" v-model="description" placeholder="Digite la nota">
                            <button type="submit" class="btn btn-success">Registrar</button>
                        </div>
                    </div>
                </form>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data () {
            return{
                description: ""
            }
        },
        mounted() {

        },
        methods: {
            newNote () {
                let params = {
                    description: this.description
                };
                axios.post('/notes', params)
                .then((response) => 
                    this.description = ''
                );
            }
        }
    }
</script>
