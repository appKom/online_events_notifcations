# Cloud function for sending firebase notfications

The Python function takes in 2 pages from the endpoint: https://old.online.ntnu.no/api/v1/event/events/.

The script sorts through registration_start, and if an events registration start is between 24 hours and 10 minuttes before the current time. It will send out a notification to subscribed users using Firebase Cloud Messaging. The subscription is divided into topic 1, 2, 3 and 4. Topic 1 is social events, 2 is courses, 3 is company presentations and 4 is other events. 

If the event_type fetched from the API is equal to subscribed topic, a notification is sent out to only the subscribed users of that topic.

The function runs as a cloud function in Google Cloud Platform and is schedualed to run 11:45 AM every day.
