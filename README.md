# Library Management System

A simple command-line application for managing a small library, written in Python. Books are stored in a local JSON file, so your data is saved between runs.

## Features

- **Add** a book with an ID, name, and author
- **View** all books with their current status
- **Search** for a book by name (case-insensitive, partial match)
- **Issue** a book to a student
- **Return** an issued book
- **Delete** a book from the library
- **Persistent storage** using `library.json`

## Requirements

- Python 3.6 or higher
- No external libraries needed (uses only `json` and `os` from the standard library)

## Getting Started

1. Save the program as `library.py` (or any name you like).
2. Open a terminal in the same folder.
3. Run:

```bash
python library.py
```

The file `library.json` is created automatically the first time you add a book.

## Usage

When the program starts you will see this menu:

```
===== LIBRARY MANAGEMENT SYSTEM =====
1. Add Book
2. View Books
3. Search Book
4. Issue Book
5. Return Book
6. Delete Book
7. Exit
```

Type the number of the option you want and press Enter.

| Option | What it does |
|--------|--------------|
| 1 | Asks for Book ID, name, and author, then saves the book as "Available" |
| 2 | Lists every book with its ID, name, author, and status |
| 3 | Finds a book whose name contains the text you enter |
| 4 | Marks a book as "Issued" and records the student's name |
| 5 | Marks an issued book as "Available" again |
| 6 | Permanently removes a book by its ID |
| 7 | Exits the program |

## Data Format

Each book is stored in `library.json` like this:

```json
{
    "id": "101",
    "name": "Python Basics",
    "author": "Jane Doe",
    "status": "Issued",
    "issued_to": "Ravi"
}
```

The `issued_to` field only exists while a book is issued.

## Project Structure

```
.
├── library.py      # Main program
├── library.json    # Auto-generated data file
└── README.md
```

## Known Limitations

- Book IDs are not checked for duplicates, so use unique IDs.
- Search returns only the first matching book.
- Deleting a book does not ask for confirmation.
- If `library.json` becomes corrupted, the program may fail to start; delete or fix the file to continue.

## Future Improvements

- Prevent duplicate IDs and empty input
- Show all search matches
- Add due dates for issued books
- Add an "Update book" option
- Move storage to SQLite

## License

This project is free to use and modify for learning purposes.
