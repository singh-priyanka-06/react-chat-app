REACT CHAT APP

To run this application :
1. npm install – to install the dependencies
2. npm start – to start the application

This Chat application is built with React JS and Chat Engine.
Chat Engine provides the server to host the chat components.
In here users can create chat rooms and add other users to chat, share images, add avatars i.e. profile picture and get notification of message sent.
Why Chat Engine?
Chat Engine makes building chat very easy for people on a budget.
It's perfect for people like freelancers and students, projects like start-ups and side-hustles.
Other SDKs such as Stream and SendBird start at $300 per month after a 14 day trial. That's too expensive!

What is Chat Engine?
Chat Engine is an api use to build chat application. 
It provides the rest api to host your chat and npm components.
It also provides server to host your chat needs and required chat components

rest api- 
While API is basically a set of functions and procedures that allow one application to access the feature of other application, REST is an architectural style for networked applications on the web. It is limited to client-server based applications. REST is a set of rules or guidelines to build a web API.

Chat engine uses sockets behind the scenes.

sockets (chat sockets): 
Sockets have traditionally been the solution around which most real-time chat systems are architected, providing a bi-directional communication channel between a client and a server. This means that the server can push messages to clients. Whenever you write a chat message, the idea is that the server will get it and push it to all other connected clients.

It has 5 components-
1. ChatFeed
2. MyMessage
3. OthersMessage
4. MessageForm
5. LoginForm


ChatFeed component renders all the other components namely, MyMessage, OtherMessage and MessageForm. MyMessage renders the loged in user message. OthersMessage renders the received messages from the other user. MessageForm renders the text input area to write the meassegs to be sent. The avatars are displayed as the read message acknowledgenent.

In the MyMessage component the user message is rendered on the right hand side of the screen in a purple color bubble. This look is similar to what we can see on other chat application like whatsapp or skype or teams etc.  In here the message corresponding to a perticular key is passed in props. Whenever the user is sends a text or an image, the type of message is verified. If it is a text, it is directly sent while in case of an image attcahment it is rendered in an image tag. The receipts of the messages are also handled by showing the avatars(profile picture) below the image or text sent.

OthersMessage component is a clone of MyMessage with the difference that the last message id is also shared in props along with the message. This is done to check if it is the first message by other user and accordingly, the avatars (profile pictures) of the other users are rendered first followed by their messages (image and text).

MessageForm provides the input text area for the user to type the text or attach an image to be sent. Here usestate hooks are used to store the currents state of the value entered and set the new value using setValue function. The value of useState hooks areis required to decide upon various event handlers to be used. In case of text messages OnChange and OnSubmit events are handled and the corresponding handleSubmit and handleChange handlers are called. HandleChange handler is used to show that the user is typing the text. In case of image attachment, handleUpload handler is called when the user clicks on upload button and the image file is sent. Here isTyping and sendMessage component are imported from react-chat-engine and the icons for image upload and send button are imported from @ant-design/icons.

LoginForm component renders the login form. It uses the useState hook to get and set the value of usename and password from the localStorage of the browser, once the user has logged-in. 
