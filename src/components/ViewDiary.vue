<template>
    <div>
        <h1>Your diary</h1>
        <ul>
            <li v-for="note in notes" :key="note.id">
                <p class="viewP">Header: {{note.header}} |
                date: {{note.date}}</p>
                <p class="viewP">{{note.text}}</p>
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
        this.notes.sort(function compare(a, b){
            let dateA = new Date(a.date);
            let dateB = new Date(b.date);
            return dateB - dateA; 
        });
    }
}

</script>

<style>
    li{
        padding: 2em;
        border: 1px solid rgb(255, 255, 255);
    }
    .viewP{
        font-size: 1.3em;
    }
    ul{
        border: 1px solid rgb(255, 255, 255);
        color: white;
        background: black;
    }
   
</style>