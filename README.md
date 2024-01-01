# MemoHub

## Overview

This Django API serves as a simple notes application, allowing users to create, retrieve, update, and delete notes through a RESTful interface. The API is built using the Tastypie library for Django.

## Getting Started

### Prerequisites

- Python 3.x
- Django
- Tastypie

### Installation

1. Clone the repository to your local machine:

        git clone <repository-url>

2. Navigate to the project directory:

        cd <project-directory>

3. Install the required dependencies:

        pip install Django && pip install django-tastypie

### Database Setup

Apply migrations to set up the database:

    python manage.py makemigrations
    python manage.py migrate

### Running the Server

Start the Django development server:

    python manage.py runserver

The API will be accessible at http://localhost:8000/api/.\
### API Usage Endpoints

<li>GET /api/note/: Retrieve a list of all notes.
<li>GET /api/note/{id}/: Retrieve details of a specific note by ID.
<li>POST /api/note/: Create a new note.<br>
Request body example in json format:

    {
        "title": "Note Title",
        "body": "Note Body"
    }

<li>PUT /api/note/{id}/: Update an existing note by ID.<br> Request body example (update title and body):

        {
          "title": "Updated Title",
          "body": "Updated Body"
        }

<li>DELETE /api/note/{id}/: Delete a note by ID.

### Authentication

The API currently uses basic authorization.<br>Ensure that you have the necessary permissions to perform CRUD operations.<br><br>
<b>Example Usage</b><br>
Retrieving all notes:

    curl http://localhost:8000/api/note/

Creating a new note:

    curl -X POST -H "Content-Type: application/json" -d '{"title": "New Note", "body": "This is a new note."}' http://localhost:8000/api/note/

<b>Updating a note:</b>

    curl -X PUT -H "Content-Type: application/json" -d '{"title": "Updated Title", "body": "Updated body content."}' http://localhost:8000/api/note/{id}/

<b>Deleting a note:</b>

    curl -X DELETE http://localhost:8000/api/note/{id}/

### License

This project is licensed under the MIT License.