<template>
    <div>
        <h1>view diarys here</h1>
        <ul>
            <li v-for="note in notes" :key="note.id">
                Header: {{note.header}} |
                date: {{note.date}}<br/>
                text: {{note.text}}<br/>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'ViewDiary',
    data(){
        return {
            notes: JSON.parse(localStorage.getItem("notes"))
        }
    },
    mounted(){
        if(localStorage.getItem("notes") === null){
            localStorage.setItem("notes", "[]")
        }
    }
}

</script>

<style>

</style>