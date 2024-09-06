# Mongodb-exercise

1. // Create a new database and switch to it
use library// Create a collection named "books"
db.createCollection("books")
// Insert a document into the "books" collection
db.books.insert({
title: "The Great Gatsby",
author: "F. Scott Fitzgerald",
published_year: 1925
})
2. Read
// Retrieve all documents from the "books" collection
db.books.find()
// Find and display only the documents where the author is "J.K. Rowling"
db.books.find({ author: "J.K. Rowling" })
// Fetch and display the document with the earliest published year
db.books.find().sort({ published_year: 1 }).limit(1)
3. Update
// Update the published year of the book with the title "The Catcher in the Rye"
db.books.update({ title: "The Catcher in the Rye" }, { $set: { published_year: 2024 } })
// Add a new field "genre" with the value "Mystery" to all documents
db.books.update({}, { $set: { genre: "Mystery" } }, { multi: true })
4. Delete
// Remove the document with the title "1984"
db.books.remove({ title: "1984" })
// Delete all documents where the published year is before 2000
db.books.deleteMany({ published_year: { $lt: 2000 } }

5. **Advanced Query:**
- Find and display the top 3 recently published books from the "books" collection.
db.books.find().sort({published_year:-1}).limit(3)
