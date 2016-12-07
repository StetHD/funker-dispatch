# funker-dispatch
HTTP dispatch for Amazon AWS triggers or Alexa SDK

Usage:
======

``
git clone https://github.com/alexellis/funker-dispatch
cd funker-dispatch
git clone https://github.com/alexellis/funker-node
docker build -t funker-dispatch .

docker run --net=funker -p 3000:3000 --name dispatch funker-dispatch
```

Technical architecture:
======================

![](https://raw.githubusercontent.com/alexellis/funker-dispatch/master/alexa-funker.png)

Sample JSON from Alexa Skills kit:
=================================

**request**

```
{
  "session": {
    "sessionId": "SessionId.dc2657cc-90cc-4343-939d-b0baf29eb690",
    "application": {
      "applicationId": "amzn1.ask.skill.4a71a0a0-d0e6-4ca7-a99b-2715e5772755"
    },
    "attributes": {},
    "user": {
      "userId": "amzn1.ask.account.AEN7KA5DBXAAWQPDUXTXFWBARZ5YZ6TNOQR5CUMV5LCCJTMBZVFP45SZVLGDD5GQBOM7QMELRS7LHG3F2FN2QQQMTBURDL5I4PQ33EHMNNGO4TXWG732Y6SDM2YZKHSPWIIWBH3GSE3Q3TTFAYN2Y66RHBKRANYCNMX2WORMASUGVRHUNBB4HZMJEC7HQDWUSXAOMP77WGJU4AY"
    },
    "new": true
  },
  "request": {
    "type": "IntentRequest",
    "requestId": "EdwRequestId.d4c65242-dd10-4270-918e-59e5222f6965",
    "locale": "en-GB",
    "timestamp": "2016-12-07T15:58:14Z",
    "intent": {
      "name": "SpaceCountIntent",
      "slots": {}
    }
  },
  "version": "1.0"
}
```

**response**

```
{
  "version": "1.0",
  "response": {
    "outputSpeech": {
      "type": "PlainText",
      "text": "There's currently 6 people in space"
    },
    "card": {
      "content": "There's currently 6 people in space",
      "title": "People in space",
      "type": "Simple"
    },
    "shouldEndSession": true
  },
  "sessionAttributes": {}
}
```