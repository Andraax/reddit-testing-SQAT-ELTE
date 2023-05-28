# reddit-testing-SQAT-ELTE
# To setup docker and gradle
### Step 1:
Copy gradle project into **tests/** folder.

### Step 2:
``` 
docker compose up
docker exec -it [container name] bash
```
### Step 3:
```cd tests/gradle_project_name```

### Step 4:
```gradle test```


# Read before you test

First, run the docker-compose.yml, this will create a docker image with a selenium firefox standalone as well as an Ubuntu machine.
To check the testing live: go to localhost:7900

Once you run the test, this will load a website containing a temporary email. It will retrieve this email and then load the Reddit registration page and parse this email as an input.
It will then take the first random username generated by Reddit, use it as the username, input a password and click the register button.

### You then have 30 seconds to MANUALLY complete the captcha and click the "Verify" button!

Wait until the timer reach 0.
After this, it will load the reddit homepage and redirect you to the temporary mail address inbox.
It will wait for the mail to arrive then open it, and click the verification link.

Once the account is verified, it will look for the cyberpunk game subreddit, confirms it loaded properly, log you out and check if the logout was successful.
