# Express All Interactions Example

This example shows a fully functioning app using the
[Slack Interactive Messages](https://github.com/slackapi/node-slack-interactive-messages) package.

## Setup

### Create and Install a Slack app

1. Create an app at <https://api.slack.com/apps> (don't close this window, you'll need it later).

2. Once you've created the app, navigate to the "Install App" page on the sidebar. You'll see a hyperlink to add a 'permission scope' -- click on this.

3. Scroll down to **Scopes**, and under the dropdown labeled **Select Permission Scopes**, select the option that says "Add slash commands and add actions to messages (and view related content)." Save your changes.

4. Click on "Install App" in the sidebar, and click on the green **Install App** button. Once you've confirmed that you want to install your app, a page with an OAuth Access Token should appear.


### Run the code

1. Choose where you want to run:
  *  Either clone this repo, navigate to this directory, and run `npm install`
  *  Or, <a href="https://glitch.com/edit/#!/remix/slack-express-all-interactions-example"><img src="https://cdn.glitch.com/2bdfb3f8-05ef-4035-a06e-2043962a3a13%2Fremix%402x.png?1513093958726" alt="remix button" aria-label="remix" height="33"></a>

2. Set the following environment variables (note: you can find these parameters in the `.env.sample` file. **If on Glitch**, copy into the `🗝.env` file and fill out there; **If local**, copy into a new `.env` file, fill that out, and run `source .env`):
  *  `SLACK_VERIFICATION_TOKEN`: Available on your app's _Basic Information_ page in Slack. Scroll down to **App Credentials** and you will see it in the textbox labeled **Verification Token**.
  *  `SLACK_ACCESS_TOKEN`: Available on your app's _Install App_ page in Slack, in the box labeled **OAuth Access Token**.
  *  `PORT`: _ONLY_ if you are running locally

3. _ONLY_ If you're running the app locally:
  *  Make sure you're on a supported version of node (see `.nvmrc` or if you have nvm run `nvm use`)
  *  Start the app (`npm start`)

### About Glitch/ngrok

The rest of the instructions will ask you either to use an ngrok URL or a Glitch URL.

* If you're running the app locally, we recommend exposing your port via [ngrok](https://ngrok.com/). If you have ngrok installed, run `ngrok http [YOUR PORT]`. Use the resultant URL henceforth.
* Alternatively, if you're working off Glitch, hit the "share button" and use the URL provided in the "Share Your App" area henceforth.

### Enable Interactive Components

1. Open your app's _Interactive Components_ page in Slack.
2. Enable interactive components and enter the Request URL and Options URL (use the same URL for both)
  *  ngrok URL or Glitch URL + '/slack/actions'

### Create a Slash Command

1. Open your app's _Slash Commands_ page in Slack.
2. Click "Create New Command"
  *  In command use: `/interactive-example`
  *  In request URL use: ngrok URL or Glitch URL + `/slack/commands`
  *  Click Save
3. On the _Install App_ page, reinstall in your Development Workspace.

## Usage

The slash command can be triggered in three ways:
*  `/interactive-example button`: Creates a message with message butons. When you click one, the message updates.
*  `/interactive-example menu`: Creates a message with a dynamic menu. When you begin typing, the options are narrowed down. Selecting an option updates the message.
*  `/interactive-example dialog`: Creates a dialog with a user menu input and text input. Sends a confirmation message after submission.
