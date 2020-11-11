# SlackBot

## What is SlackBot?

This is a package for running a Bot on Slack as a Flask app.
The [event handling modules](./event_handling) create a framework for 
processing all events in [threads](./event_handling/event_processor), pulled from an [event queue](./event_handling/event_queue).
This is necessary as the Slack API will duplicate any requests if it does not hear back within 3 seconds, 
and many events may require longer processsing time, thus it can be bypassed by passing all payloads to 
the [event handler](./event_handling/event_handler), allowing the bot to immediately respond HTTP 200 OK.

Some additional modules include [models](./models) for Slack events and replies. These are wrapper objects
that extend some extra functionality. In the case of [replies](./models/slack_reply), we can pass in a string or a
string returning function to get a reply unique to the user. There is a [chat features](./chat_features) module containing
a reaction based poll implementation, and more useful chat interactions in the future.

## How can I run it?

