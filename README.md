# listobjectsbot

Sends a summary of recently-modified objects from [`listObjects()`](http://jenkins-1.dataone.org/jenkins/job/API%20Documentation%20-%20trunk/ws/api-documentation/build/html/apis/MN_APIs.html#MNRead.listObjects) to Slack via webhook URL. This
script is designed to be run via a cron job. Every time the script is run, it
queries `listObjects()` for objects modified between the last time the script
was run and the current time.

## Dependencies

- I have developed and tested this with Python 3.5.1
- Extra packages (install via requirements.txt):
  - [requests](http://docs.python-requests.org/en/master/)
  - [python-dotenv](https://github.com/theskumar/python-dotenv)
  - [python-rt](https://gitlab.labs.nic.cz/labs/python-rt)

## Setup

- Run `pip install -r requirements.txt`
- Create a file called `.env` in the same directory as the script

  Include the following variables:

  ```
  LASTFILE_PATH=LASTRUN       # Determines where the bot stores its state
  SLACK_WEBHOOK_URL="{URL}"   # Your Slack webhook URL
  USERS="@you @me @everyone"  # Who you want to direct the message to
  ```

## Running

Run `python bot.py`
