- 👋 Hi, I’m @Tchelet-Perlmutter
- 👀 I’m interested in BackEnd development...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on Kapachi2 project I am working on...
- 📫 How to reach me tchelet.perlmutter@gmail.com or https://www.linkedin.com/in/tchelet-perlmutter-427a25165/...



Hey there :)
I am excsited to introduce my chat app project (Kapachi2) to you.
I'll start with the explanation of the app idea, and then elaborate about the possible actions that can be done with the current code.
---------------------------------- 

###  The idea:

--------------------

### The problem Kpachi solves:

There are many important things that people don't say enough to each other or don't say in a proper way that will create the wished impact on the other person.
Here are three examples for such things people are not saying enough:

"Thank you for doing ... It effected me in ... way / It made me feel..."
"Sorry for... My intention was to... How can I be better next time?"
"It seems to me that when you are doing... it hurts you/others in ... way, and I'm not sure if you are doing it because you are not aware of that, or because there is some good reason to do so despite 'what I mentioned. Do you think I might be right?"
There are many possible reasons for avoiding such kind of messages. For instance - fear of angry/defensive response, or transmitting neediness, weakness, or lack of self-confidence.

None of those reasons is good enough to justify avoidant from giving those huge gifts we can give to each other every day. It is just too easy to not do that, given the fact that when we do choose to say, we risk our image, without receiving an immediate certainly enough reward for that.

In other words - there is a huge, easy to create, potential value, that is not being created just because there is no way to pay for it without distorting it by that.

The resolute - we love less, Improve ourselves less, angry more and lonely for a terrible extent

### How does Kapachi work and how can it decrease this problem?

Let's say a user got in Kapachi app a gifting message, i.e. a message with a nice template as I wrote above, and he wants to read it. That user won't be able to read that message till he will send a gifting-message ass well, to two other people. As you guessed, that rule is valid to those two people, which means that if the template is good, i.e. make people write important and honest things to each other, It will be distributed exponentially.

The principle is very simple - Kapachi is the way to make people "pay" for that fantastic value, without destroying it by that.

----------------------------------

### What can be done with the code?

-------------------------

Kapachi2 repository contains an API that allows sending CRUD requests for the next four collections: messages, groups, users, and conversations.

- [ ] **Each of the collections can be searched by:**

- All existing Documents of type X
- All the documents of collection X that belong to another document of collection Y, which can be defined by its id or by some query.
E.g. "All the messages of the user/conversation with the id 948563857". Another example -  "All the conversations of the user with 'name' field that equivalents to 'Tchelet'.
- The document with the id X
- All the documents that feet the conditions of query X

- [ ] **When adding a new gifting message with an addressee that is not signed up yet:**

The handler function creates a new minimalistic user for the addressee, then creates a new conversation for that new user and the sender, then add that new message to the conversation, and then change the "to" field of the new message to be the _id that mongo created for the new minimalistic user was created

- [ ] **When the message is the first message that was sent between two users:**

The handler creates a new conversation for them automatically 

- [ ] **When a new conversation is created**, the handler adds its _id to the 'conversationalistsIndexesArr' field of its conversationalists' user's documents. In case of new message creation, its _id is added to the messagesIndexesArr of its conversation


- [ ] **When a new message is created**, the _id of the addressee is added to the 'lastTenGiftedArr' field of the sender. Users have to send the gifting messages to ten different people before they allow to send again to one of them. That is in order to encourage users to go out of their comfort zone, and surprise themselves with new deep relationships they haven't thought could be deep before 

- [ ] **When a new gifting message is created**, Kapachi sends an SMS to the addressee, that invites him to the app/site, so that he would be able to send two messages and then open the message he got.

-------------------
### Planed futures:

* Create a permanent password to that new user, that will be sent with the SMS, and will make it easier for him to be rewarded faster.

* Get permission to the user's contacts from Facebook and from his phone so that Kapachi could offer him options for contacts to send messages to
