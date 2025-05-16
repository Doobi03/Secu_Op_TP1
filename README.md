# Password Strength Checker API

## Description

(TO BE COMPLETED BY STUDENTS: Briefly describe the project - e.g., an API that analyzes a given password and returns its estimated strength and suggestions for improvement.)

## Prerequisites

(TO BE COMPLETED BY STUDENTS: List what is needed to run this project locally, e.g., Python 3.8+ and pip.)

## Installation

1.  Clone this repository:
    ```bash
    # git clone <repository_url>
    # cd <repository_name>
    ```
2.  Create and activate a Python virtual environment:
    ```bash
    python -m venv venv
    # On macOS/Linux:
    source venv/bin/activate
    # On Windows (PowerShell/cmd):
    # venv\Scripts\activate
    ```
3.  Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

## Running the Application

To run the FastAPI application locally using Uvicorn:
```bash
uvicorn main:app --reload
```
The application will typically be available at http://127.0.0.1:8000. The interactive API documentation (Swagger UI) can be found at http://127.0.0.1:8000/docs.

## API Endpoints

(TO BE COMPLETED BY STUDENTS: Describe each API endpoint, its purpose, request body/path parameters, and an example of the expected JSON response or behavior.)


* POST /check_password_strength
La fonction vérifie les critères de longueur, de caractères majuscules/minuscules/spéciaux et chiffres contenus dans le mot de passe. Plus de critères sont remplis et plus le score associé au mot de passe est fort. Dans le cas où les critères viennent à manquer, on envoie un message des critères suggérés à rajouter pour rendre le mdp plus fort.

  * Description: On analyse le mot de passe yourPassword123 composé de plus de 11 caractères (correspond à un mdp long, +2 de score), de majuscules et minuscules (+2) et des chiffres (+1). Il lui manque des symboles spéciaux qui sont suggérés
  * Request Body: {"password": "yourPassword123"}
  * Example Response (200 OK):
  ```json
    {
        "password": "yourPassword123", 
        "strength": "good", 
        "score": 5,
        "suggestions": ["Add symbols (e.g., !@#$%)"]
    }
  ```

* GET /health_strength_checker
  * Description: Health check for this API. Vérifie que le statut de mot de passe est bien lancé
  * Response: {"status_strength_checker": "ok"}

## Project Structure

* main.py: Contains the FastAPI application logic for the password strength checker.
* requirements.txt: Lists the Python dependencies.
* tests/: Contains the automated tests.
* .gitlab-ci.yml: Defines the GitLab CI/CD pipeline.
* README.md: This file.
* pip-audit -r requirements.txt: Permet de vérifier les vulnérabilités des dépendances
* écrites dans requirements.txt. Affiche: No known vulnerabilities found 

- Etape 5: