# Slack Your Future Project : Back End

In this project, you will have the opportunity to demonstrate the listed skills. 

 <details><summary>Learning Outcomes</summary>
The hard skill assessment will review on what you have accomplished on this project based on the deliverables that are set under.

🥚 Git Remote/Local Connection: You can create a local git repository, commit changes, connect a remote repository and push changes to the remote.

🥚 Linting: You can find and fix linting errors in JavaScript programs.

🥚 Git Branching Workflow: You can manage your work locally using branches: pull remote changes -> create a new branch -> push the branch to the remote repository -> open a PR with passing Continuous Integration checks -> merge changes to main/master.

🥚 Command Line Interface (CLI): You can navigate a directory, manage folders/files, make small changes in a file using nano/vim, and much more

🥚 Design Cycle: You will be able to describe the design cycle and what steps you will take in each state (Empathize, define, ideate, prototype, testing and implement).

🥚 Fixing Errors: You can use the structured comment to describe an error in your program, and can make several educated guesses at how to fix the error.

🐣 Testing Existing Functions: You can write unit tests for a working function using the describe/it/expect(_).toEqual(_) syntax. This includes grouping test cases into logical test suites.

🐣 You can write small programs with a good component-based design that asynchronously uses data stored in different locations:
• Browser: You can write a small web page that fetches data from a RESTful API and renders it into the DOM.

🐣 design, plan, build small web page using React that fetches data from an API
  </details>


<details><summary>What else to demonstrate?</summary>
🥚code review deliverables : your PRs meet these standards:

    • PR has a descriptive title
    • PR has appropriate labels and milestones for easy identification
    • Reviewers are assigned
    • the PR contributes only one focused change
    • It is in the appropriate column in the project board
    • has short and clear description
    • is linked to an issue
    • feedback is addressed (if any)


🥚 retrospective deliverables : you have shared your retrospective for each sprint on your project
  </details>
<details><summary> Project- idea (Slack-clone) </summary>

Your goal is to build a Slack clone. You will use the base HTML/CSS code supplied. The application will allow registered users to login and send and receive messages.

### Messaging
- [ ] Messages can contain a link to an external platform, an image, and rich text. 
- [ ] Messages can be sent one-to-one in a direct conversation from a sender to a receiver
- [ ] Messages can be sent to channel in order to support group discussions. Such a channel will always have name, and a list of members.

</details>

---

## Few tips to follow

* **start with wireframe** :whether you are working on the UI or on the data design, it is a good to know where you want to end up to. Design your wireframe and data-model first.

* **Start small**: start your coding journey from the smallest component you think of. This can be only connecting the pages that you are going to design and increment your work step by step.

* **One feature one pull request**: by keeping your feature branch as specific as possible, you will save time from uncessary conflicts and errors

* **Don't rush, understand!**: like we always say,It's better to study slowly and learn from your mistakes than to code quickly and not understand what you wrote.



## Using the app

- **from postman**
  - `http://localhost:xxxx/api` - the main entry point to the API
- **from the browser**
  - `http://localhost:xxxx/` - serves `/client/index.html`, the chat client that will connect to your API routes.
  - you can also use the API routes, but it will be less helpful than in Postman

<details><summary>The API Documentation</summary>

## Channels

Fetch Channels
----

  Returns json data about all channels in the system.

- **URL**

  /channels

- **Method:**

  `GET`

- **Result:**
  
    ```json
    [
      {
        "name": "Awesome Channel",
        "id": "ZAE12E124321ZE"
      },
      ...
    ]
    ```
  
---

Fetch Channel
----

  Returns json data about a single channel.

- **URL**

  /api/channels/:channelId

- **Method:**

  `GET`
  
- **URL Params**

   **Required:**

   `channelId=[string]`

- **Result:**
  
    ```json
    {
      "name": "Awesome Channel",
      "id": "ZAE12E124321ZE"
    }
    ```

---

Delete Channel
----

  Removes a channel from the system.

- **URL**

  /api/channels/:channelId

- **Method:**

  `DELETE`
  
- **URL Params**

   **Required:**

   `channelId=[string]`

- **Result:**
  
    ```json
    { 
      "message": "Channel ZAE12E124321ZE was successfully deleted!"
    }
    ```

---

Update Channel
----

  Replaces a channel with its updated version.

- **URL**

  /api/channels/:channelId

- **Method:**

  `PUT`
  
- **URL Params**

   **Required:**

   `channelId=[string]`

- **Body**

   ```json
   {
     "name": "new name of the channel",
     "id": "the channel id"
   }
   ```

* **Result:**
  
    ```json
    {
      "name": "Awesome Channel",
      "id": "ZAE12E124321ZE"
    }
    ```

---

Create Channel
----

  Creates a new channel with the given name.

- **URL**

  /api/channels

- **Method:**

  `POST`
  
- **Body**

   ``` json
   {
     "name": "the name of the channel you wish to create",
   }
   ```

- **Result:**
  
    ```json 
    {
      "name": "Awesome Channel",
      "id": "ZAE12E124321ZE"
    }
    ```

---

## Messages

Get all messages
----

  Returns a json array of all messages currently in the system.

- **URL**

  /api/messages

- **Method:**

  `GET`

- **Result:**
  
    ```json
    [
    {
      "text": "The content of the massage",
      "id": "BFE12E1243211ZE",
      "user": "Name of the user who posted the message",
      "date": "2021-08-13T18:25:43.511Z",
      "channelId": "ZAE12E124321ZE"
    },
    ...
    ]

---

**Get messages for a specific channel**
----

  Returns a json array of all messages that belong to the specified channel.

- **URL**

  /api/channels/:channelId/messages

- **Method:**

  `GET`
  
- **URL Params**

   **Required:**

   `channelId=[integer]`
- **Result:**
  
    ```json
    [
    {
      "text": "The content of the massage",
      "id": "BFE12E1243211ZE",
      "user": "Name of the user who posted the message",
      "date": "2021-08-13T18:25:43.511Z",
      "channelId": "ZAE12E124321ZE"
    },
    ...
    ]

---

**Delete message**
----

 Removes the specified message from the system.

- **URL**

  /api/messages/:messageId

- **Method:**

  `DELETE`
  
- **URL Params**

   **Required:**

   `messageId=[integer]`
- **Result:**
  
    ```json
    {
      "message": "Message BFE12E1243211ZE was successfully deleted!"
    }
    ```

---

**Update message**
----

 Updates the specified message with the new content.

- **URL**

  /api/messages/:messageId

- **Method:**

  `PUT`
  
- **URL Params**

   **Required:**

   `messageId=[integer]`

- **Body**

   ```json
   {
      "text": "The content of the massage",
      "id": "BFE12E1243211ZE",
      "user": "Name of the user who posted the message",
      "date": "2021-08-13T18:25:43.511Z",
      "channelId": "ZAE12E124321ZE"
    }
   ```

- **Result:**
  
    ```json
    {
      "text": "The content of the massage",
      "id": "BFE12E1243211ZE",
      "user": "Name of the user who posted the message",
      "date": "2021-08-13T18:25:43.511Z",
      "channelId": "ZAE12E124321ZE"
    }
    ```

---

**Create new message**
----

 Creates a new messsage in the specified channel.

- **URL**

  /api/channels/:channelId/messages

- **Method:**

  `POST`
  
- **URL Params**

   **Required:**

   `channelId=[integer]`

- **Body**

   ```json
   {
      "text": "The content of the massage",
      "user": "Name of the user who posted the message",
    }
   ```

- **Result:**
  
    ```json
    {
      "text": "The content of the massage",
      "id": "BFE12E1243211ZE",
      "user": "Name of the user who posted the message",
      "date": "2021-08-13T18:25:43.511Z",
      "channelId": "ZAE12E124321ZE"
    }
    ```---
</details>
