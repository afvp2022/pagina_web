<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8">
                <div class="card">
                    <div class="card-header">Detalle de Notas</div>

                    <div class="card-body">
                        <div v-for="note in array_notes" :key="note.id">
                            <p> {{ note.description }} </p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data () {
            return{
                array_notes: [{'id': 1,'description': 'Esto es una prueba #1'}, {'id': 2,'description': 'Esto es una prueba #2'}]
            }
        },
        mounted() {
            axios.get('/notes')
                .then((response) => 
                    //response.data.forEach(element => console.log(element))
                    this.array_notes = response.data
                );
        }
    }
</script>
