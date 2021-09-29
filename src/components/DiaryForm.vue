<template>
    <form @submit="handleSubmit">
        <p class="header">Header:</p> <input type="text" id="header">
        <p class="date">Date:</p> <input type="date" id="date">
        <p class="text">Text:</p> <textarea type="text" id="text"></textarea>
        <button >Save</button>
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
            alert("Diary saved!");
        }
    }
}
</script>

<style>
    form{
        height: 50em;
        background: rgb(0, 0, 0);
        color: white;
    }
  
    textarea{
        width: 100%;
        height: 400px;
        padding: 12px 20px;
        box-sizing: border-box;
        border: 2px solid #ccc;
        border-radius: 4px;
        background-color: #f8f8f8;
        font-size: 16px;
        resize: none;
        grid-row-start: 4;
        grid-column-start: 1; 
        grid-column-end: 2;
    }
    button{
        display:inline-block;
        padding:0.35em 1.2em;
        border:0.1em solid #FFFFFF;
        margin:0 0.3em 0.3em 0;
        border-radius:0.12em;
        box-sizing: border-box;
        text-decoration:none;
        font-family:'Roboto',sans-serif;
        font-weight:300;
        color:#FFFFFF;
        text-align:center;
        transition: all 0.2s;
        background: black;
    }
    button:hover{
        cursor: pointer;
        color:#000000; 
        background-color: #FFFFFF ;
    }
</style>