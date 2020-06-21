# Full Stack Trivia API 

This project is a game where users can test their knowledge answering trivia questions. implementing the following functionality:

- Display questions.
- Delete questions.
- Create new question.
- Search for questions.
- Play the quiz game.


### Installing Dependencies

this project should already have Python3, pip, node, and npm installed.


## Running Your Frontend in Dev Mode

The frontend app was built using create-react-app. In order to run the app in development mode use ```npm start```. You can change the script in the ```package.json``` file. 

Open [http://localhost:3000](http://localhost:3000) to view it in the browser. The page will reload if you make edits.<br>

```bash
npm start
```



## Running the server

From within the `backend` directory first ensure you are working using your created virtual environment.

To run the server, execute:

```bash
export FLASK_APP=flaskr
export FLASK_ENV=development
flask run
```



## Testing
To run the tests, run
```
dropdb trivia_test
createdb trivia_test
psql trivia_test < trivia.psql
python test_flaskr.py
```


### API Reference

## Getting Started
Backend Base URL: http://127.0.0.1:5000/
Frontend Base URL: http://127.0.0.1:3000/
Authentication: Authentication or API keys are not used in the project yet.
Error Handling
Errors are returned in the following json format:

```
 "success": "False",
  "error": 422,
  "message": "unprocessable",
```
The error codes currently returned are:

- 400 – bad request
- 404 – resource not found
- 422 – unprocessable
- 500 – internal server error

## Endpoints

### GET /categories

- Returns all the categories.
- for test : ```curl http://127.0.0.1:5000/categories```
- output
 ```
    
  "categories": {
    "1": "Science",
    "2": "Art",
    "3": "Geography",
    "4": "History",
    "5": "Entertainment",
    "6": "Sports"
  },
  "success": true
}
```



### GET /questions

- Returns all questions.
for test : ```curl http://127.0.0.1:5000/questions```
- output
 ```
    
"categories": {
    "1": "Science",
    "2": "Art",
    "3": "Geography",
    "4": "History",
    "5": "Entertainment",
    "6": "Sports"
  },
  "current_category": [
    5,
    5,
    4,
    5,
    6,
    6,
    4,
    3,
    2,
    2
  ],
  "questions": [
    {
      "answer": "Apollo 13",
      "category": 5,
      "difficulty": 4,
      "id": 2,
      "question": "What movie earned Tom Hanks his third straight Oscar nomination, in 1996?"
    },
    {
      "answer": "Tom Cruise",
      "category": 5,
      "difficulty": 4,
      "id": 4,
      "question": "What actor did author Anne Rice first denounce, then praise in the role of her beloved Lestat?"
    },
    {
      "answer": "Maya Angelou",
      "category": 4,
      "difficulty": 2,
      "id": 5,
      "question": "Whose autobiography is entitled 'I Know Why the Caged Bird Sings'?"
    },
    {
      "answer": "Edward Scissorhands",
      "category": 5,
      "difficulty": 3,
      "id": 6,
      "question": "What was the title of the 1990 fantasy directed by Tim Burton about a young man with multi-bladed appendages?"
    },
    {
      "answer": "Brazil",
      "category": 6,
      "difficulty": 3,
      "id": 10,
      "question": "Which is the only team to play in every soccer World Cup tournament?"
    },
    {
      "answer": "Uruguay",
      "category": 6,
      "difficulty": 4,
      "id": 11,
      "question": "Which country won the first ever soccer World Cup in 1930?"
    },
    {
      "answer": "George Washington Carver",
      "category": 4,
      "difficulty": 2,
      "id": 12,
      "question": "Who invented Peanut Butter?"
    },
    {
      "answer": "Lake Victoria",
      "category": 3,
      "difficulty": 2,
      "id": 13,
      "question": "What is the largest lake in Africa?"
    },
    {
      "answer": "Escher",
      "category": 2,
      "difficulty": 1,
      "id": 16,
      "question": "Which Dutch graphic artist\u2013initials M C was a creator of optical illusions?"
    },
    {
      "answer": "One",
      "category": 2,
      "difficulty": 4,
      "id": 18,
      "question": "How many paintings did Van Gogh sell in his lifetime?"
    }
  ],
  "total_questions": 24
}
```

### DELETE /questions/int:id\

- Deletes a question by id.
for test : ```curl -X DELETE http://127.0.0.1:5000/questions/18 ```
- output
 ```
  "deleted": 18,
  "success": true
```

### POST /questions

- Creates a new question.
for test : ```curl -X POST -H "Content-Type: application/json" -d '{ "question": "Frankie Fredericks represented which African country in athletics?", "answer": "Namibia", "difficulty": 3, "category": "6" }' http://127.0.0.1:5000/questions```
- output
 ```
"created": 33,
"success": true

 ```


### POST /questions/search

- returns questions that has the search substring.
for test : ```curl -X POST -H "Content-Type: application/json" -d '{"searchTerm": "Africa"}' http://127.0.0.1:5000/questions/search  ```
- output

 ```  
  "current_category": [
    3
  ],

  "questions": [
    {
      "answer": "Lake Victoria",
      "category": 3,
      "difficulty": 2,
      "id": 13,
      "question": "What is the largest lake in Africa?"
    }
  ],
  "total_questions": 1
}
```

### GET /categories/int:id\/questions

- Gets questions by category using the id.
for test : ```curl http://127.0.0.1:5000/categories/1/questions ```
- output
 ```

  "questions": [
    {
      "answer": "The Liver",
      "category": 1,
      "difficulty": 4,
      "id": 20,
      "question": "What is the heaviest organ in the human body?"
    },
    {
      "answer": "Alexander Fleming",
      "category": 1,
      "difficulty": 3,
      "id": 21,
      "question": "Who discovered penicillin?"
    },
    {
      "answer": "Blood",
      "category": 1,
      "difficulty": 4,
      "id": 22,
      "question": "Hematology is a branch of medicine involving the study of what?"
    },
    {
      "answer": "",
      "category": 1,
      "difficulty": 1,
      "id": 29,
      "question": ""
    },
    {
      "answer": "",
      "category": 1,
      "difficulty": 1,
      "id": 30,
      "question": ""
    },
    {
      "answer": "",
      "category": 1,
      "difficulty": 1,
      "id": 31,
      "question": ""
    },
    {
      "answer": "",
      "category": 1,
      "difficulty": 1,
      "id": 32,
      "question": ""
    }
  ],
  "total_questions": 7
}


 ```


### POST /quizzes

- Takes the category and previous questions in the request.
- Return random question not in previous questions.

for test : ```curl -X POST -H "Content-Type: application/json" -d '{"previous_questions": [5, 9], "quiz_category": {"type": "History", "id": "4"}}' http://127.0.0.1:5000/quizzes  ```
- output
 ```
"question": {
    "answer": "George Washington Carver",
    "category": 4,
    "difficulty": 2,
    "id": 12,
    "question": "Who invented Peanut Butter?"
  },
  "success": true
}

 ```








