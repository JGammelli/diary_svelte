<template>
    <form @submit="handleSubmit">
        Header: <input type="text" id="header"><br/>
        Date: <input type="date" id="date"><br/>
        Text: <input type="text" id="text"><br/>
        <button>Spara</button>
    </form>
</template>

<script>
export default {
    name: 'DiaryForm',
    
    data(){
        return{
            notes : JSON.parse(localStorage.getItem("notes"))
        }
    },
    methods: {
        handleSubmit(event){
            event.preventDefault();
            let newNote = {
                header: event.target.header.value,
                date: event.target.date.value,
                text: event.target.text.value
            }
            this.notes.push(newNote);
            localStorage.setItem("notes", JSON.stringify(this.notes));
        }
    }
}
</script>

<style>

</style>