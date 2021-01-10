

## Django Rest Framework project to handle user authentication 


## Users could use the following authentication schemes:
    BasicAuthentication
    SessionAuthentication
    TokenAuthentication

### using BasicAuthentication:
    http -a yourusername localhost:8000/book/ title='book 12'
    {
        "id": 10,
        "owner": "yourusername",
        "title": "book 12",
    }

### using SessionAuthentication:
    use the borwsable API

### using TokenAuthentication:

    step 1: obtain auth token
        http POST localhost:8000/obtain-auth-token/ username='yourusername' password='yourusernamepassword'
        {
            "email": "yourusername@gmail.com",
            "token": "efa0b636c88325dcd8d5aacd6f45f00c6606274a",
            "user_id": 1,
        }

    step 2: make post request with the Token 
        http localhost:8000/book/ title='book 12' "Authorization: Token efa0b636c88325dcd8d5aacd6f45f00c6606274a"
        {
            "id": 11,
            "owner": "yourusername",
            "title": "book 12",
        }


