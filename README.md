# Additional documentation for the api

Handy interface for testing the api on the main page:
    Swagger url '/'
    Redoc url '/redoc/'
    
    There are get/post/put examples and everything you need )
    
Warning: 
If you want to test api/v1/interview/{id}/interview/ in swagger or redoc !
This is the url for the survey test, you will need to write json manually in the post for technical reasons 
    
    

# important points and sample queries 

1) api/v1/interview/{id}/interview/ - url of the survey pass

        Example request:
            {
                { "user": 1,
                { "anonymously": false,
                { "answers": [
                    {
                       
                        { "choices": [1] (id of answer choice),

                        { "question": {
                                    "id": 1,
                                    "question_type": 1 (0-answer text, 1-answer with one choice, 2-answer with several choices)

                                     },
                   },
  
              ]
            }
            
        
- The answer object is one in this case, i.e. an answer to one question
- pass the question_type, so that queries are not cloned


2) /api/v1/user/ - url To register users
3) /api/v1/rest-auth/ login/logout For login and logout
  Query example: 
  {
    "username": "string",
    "password": "string"
  }
  
  In reply you'll get a user object and a token
 
4) Also after adding start_time in the 
  create/update/delete its requests disappear


# Instructions for deploying the project on your computer
    
    1) The project uses a postgresql database, so you have to create it
        CREATE DATABASE test_task_db;
    
    2) Do the migration:
        Applications must be specified !
        python manage.py makemigrations interview user
        python manage.py migrate
    
    3) Create user:
        python manage.py createsuperuser 
       
    4) Static:
        python manage.py collectstatic
        
    5) Run the project
        python manage.py runserver
        
Enjoy :)
