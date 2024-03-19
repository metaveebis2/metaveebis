# AR.js Studio

AR.js Studio is an authoring platform to build Web Augmented Reality experiences, without coding knowledge.

[Learn more](https://medium.com/@nicolcarpignoli/ar-js-studio-a-call-to-arms-for-the-first-open-source-web-ar-authoring-platform-a031069518f9)

<img src="https://i.ibb.co/nz1ydkR/Schermata-2020-04-11-alle-13-48-16.png"/>


## If the publish on Github step fails

It is probably due to the external server handling oAuth2.0 requests.
We are using this project: https://github.com/prose/gatekeeper/ to handle the oAuth2.0 requests.
The project is now hosted on a private server, and it is not guaranteed to be always up and running.
If the publish fails, you should:

- fork the arjs studio project (because you need to change the `publish-confirm.js` file)
- host is somewhere else (even your GitHub pages)
- find a node server that can host the gatekeeper project
- set up the server with the gatekeeper project: you have to set, on the `config.json` file, the `GITHUB_CLIENT_ID` and `GITHUB_CLIENT_SECRET` [with the ones you get from the github oAuth app you create](https://docs.github.com/en/rest/authentication/authenticating-to-the-rest-api?apiVersion=2022-11-28)
- be aware that gatekeeper is listening on port 9999 by default, use that on your server
- on `studio` project, change the current URL on `publish-confirm.js` file line 21, with the new getekeeper server URL

All the other functionalities (and studio-backend project) should work as expected.