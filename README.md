# Student Management with MongoDB Atlas and Python

This project is a Python console application that allows you to manage a student database stored in MongoDB Atlas. It uses the `pymongo` library to interact with the database, offering CRUD (Create, Read, Update, Delete) functionality through an interactive menu.

## Features

* **Secure Connection**: Connects to a cloud-based MongoDB Atlas database.
* **Add Students**: Allows adding new student records with name, age, and major.
* **List Students**: Displays all students stored in the database.
* **Update Age**: Modifies the age of an existing student.
* **Delete Students**: Removes student records from the database.
* **Interactive Menu**: Simple console-based user interface for easy interaction.

## Technologies Used

* **Python 3.x**
* **PyMongo**: Official MongoDB driver for Python.
* **MongoDB Atlas**: Cloud database service.

## Project Setup

Follow these steps to run the project in your local environment:

### 1. Clone the Repository (or download the notebook)

If you're using this code from a GitHub repository, clone it:

```bash
git clone <YOUR_REPOSITORY_URL>
cd <YOUR_REPOSITORY_NAME>
```

If you're using Google Colab, simply run the cells in order.

### 2. Install Dependencies

Make sure you have `pymongo` installed. You can install it using `pip`:

```bash
pip install --upgrade pymongo
```

### 3. Configure Your MongoDB Atlas Connection String

You’ll need a MongoDB Atlas account and a configured database. Once your cluster is ready, get your connection string (URI):

1. Log in to your MongoDB Atlas account.
2. Go to your cluster.
3. Click on **Connect**.
4. Select **Connect your application**.
5. Copy the connection string. Make sure to replace `<username>` and `<password>` with your actual credentials, and optionally `<dbname>` with your database name.

**Update the code**: In the cell where `cliente = MongoClient(...)` is defined, replace the existing connection string with yours:

```python
cliente = MongoClient("mongodb+srv://<username>:<password>@cluster0.kgm2etf.mongodb.net/?retryWrites=true&w=majority")
```

**Important!** Make sure the database user you’re using has the proper permissions (read and write) for the database and collections you’ll be working with (`BD_CursoMongo` and `Estudiantes` in this case).

## Usage

Once everything is set up and dependencies are installed, run the notebook (or Python script). The program will display an interactive menu in the console:

```
--- STUDENT MENU ---
1. Add student
2. List students
3. Update student age
4. Delete student
5. Exit
Select an option:
```

Simply enter the number of the option you want and follow the instructions.

### Example Interaction

1. Select `1` to add a student.

   * `Enter the student's name: Kevin Luengas`
   * `Enter the student's age: 20`
   * `Enter the student's major: Data Science`
   * `Student Kevin Luengas added.`

2. Select `2` to list students.

   * `Student list:`
   * `{'_id': ObjectId('...'), 'name': 'Kevin Luengas', 'age': 20, 'major': 'Data Science'}`

3. Select `5` to exit the program.

   * `Exiting the program.`

## Code Structure

The code is organized into functions for each CRUD operation:

* `insertar_estudiante(nombre, edad, carrera)`: Adds a new student.
* `listar_estudiantes()`: Retrieves and displays all students.
* `actualizar_edad(nombre, nueva_edad)`: Updates a student’s age by name.
* `eliminar_estudiante(nombre)`: Deletes a student by name.
* `menu_estudiantes()`: Main function that displays the menu and handles user interaction.

## Contributions

Contributions are welcome. If you find a bug or have a suggestion for improvement, feel free to open an issue or submit a pull request.

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.
