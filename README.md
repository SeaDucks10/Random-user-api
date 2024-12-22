# Random-user-api
# its generates a random user with the help of the random user api

import requests

def get_random_user():
    # Make a GET request to the Random User API
    response = requests.get("https://randomuser.me/api/")
    
    # Check if the request was successful
    if response.status_code == 200:
        # Parse the JSON response
        data = response.json()
        
        # Retrieve user details
        user = data['results'][0]
        first_name = user['name']['first']
        last_name = user['name']['last']
        email = user['email']
        phone = user['phone']
        
        # Print user information
        print(f"First Name: {first_name}")
        print(f"Last Name: {last_name}")
        print(f"Email: {email}")
        print(f"Phone: {phone}")
    else:
        print("Failed to retrieve data from the Random User API")

# Run the function
get_random_user()

