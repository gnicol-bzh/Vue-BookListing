<template>
    <div>
        <h1>{{ title }}</h1>
        <ul>
            <book-item v-for="book in books" :book="book" />
        </ul>
        <book-form @addBook="appendBook"></book-form>
    </div>
</template>

<script>
import BookForm from "./BookForm";
import BookItem from "./BookItem";
export default {
    name: "BookList",
    data: function() {
        return {
            books: [
                { title: "Self-Reliance", author: "Ralph Waldo Emerson" },
                { title: "American Gods", author: "Neil Gaiman" },
                { title: "Amusing Ourselves to Death", author: "Neil Postman" }
            ],
            title: "All Books"
        };
    },
    components: {
        BookForm,
        BookItem
    },
    methods: {
        appendBook(bookTitle, bookAuthor) {
            this.books.push({ title: bookTitle, author: bookAuthor });
        }
    }
};
</script>

<style>
h1,
h2 {
    font-weight: normal;
}
ul {
    list-style-type: none;
    padding: 0;
}
</style>
