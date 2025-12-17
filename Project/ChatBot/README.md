# 🤖Chatbot Project

This project is a chatbot developed by our group to provide interactive and intelligent conversations with users. It is designed to be simple, flexible, and easy to expand for different use cases such as customer support, learning assistance, or general conversation.

## 🤺Amazon Lex V2 Bot Creation

**1. Creating a Bot in Amazon Lex V2 Console**

I began by navigating to the Amazon Lex V2 Console. Once there, I clicked Create bot. I chose
the Traditional creation method and selected the option to create a blank bot.

I entered a bot name and added a short description. For IAM permissions, I let Lex create a new
role with basic permissions, which is recommended for new bots. I set COPPA compliance as
appropriate, kept the default idle session timeout, and added tags for resource management.

Finally, I clicked Next.

Next, I added a language. I chose English (US) as the primary language, selected a voice for
speech responses, and kept the default intent classification confidence threshold. After that, I
clicked Add language and then Done.

At this point, I reviewed the bot overview. The bot was ready for me to add intents, slots, and
utterances. This gave me a solid foundation with the right permissions and configuration.

**2. Designing Intents, Utterances, and Slot Types**

When designing the conversation, I focused on user goals and natural language. I made sure
prompts sounded conversational, offered clear options, and handled errors gracefully.
To create intents, I clicked Add intent → Add empty intent. I named each intent and added
descriptions. Then I provided at least 10 varied utterances per intent. 

For example:

 Quiz intent: “I want to take a quiz”, “Start the knowledge quiz”, “Quiz me”

 Answer intent: “The answer is {Answer}”, “I choose {Answer}”, “My answer is
{Answer}”

I added slots where needed. For multiple-choice answers, I created a custom slot type with
values like A, B, C, and D. I configured prompts, confirmation messages, and closing responses
so the bot could guide the user smoothly.

**3. Building Multi-Turn Dialogs**

I wanted the bot to handle multi-turn dialogs, so I designed it to ask questions one at a time,
capture answers, and provide feedback.
For example:

 User: “Start quiz”
 Bot: “Question 1: What is the capital of France? A) Paris B) Berlin C) Rome D) Madrid”
 User: “A”
 Bot: “Correct! Next question…”

I used session attributes to track quiz state and Lambda functions to manage logic. I made sure
the bot gave clear prompts, reminded users of context, and allowed corrections before moving
on.

**4. 😁Integrating AWS Lambda**

To make my quiz bot truly interactive, I wrote a Lambda function in Python. This function
handled the quiz logic, validated answers, tracked scores, and managed the conversation flow.
Here’s how I approached it:

 Quiz Questions: I defined a list of 15 multiplechoice questions about Amazon S3. Each
question included an ID, the text, three possible options, and the correct answer. This
gave me a structured dataset to work with inside the Lambda function.

 Lambda Handler: My lambda_handler function received events from Lex. It checked
the intent name (like StartQuiz, QuizIntent, or FallbackIntent) and decided what
to do next.

o If the user said “start quiz,” the function initialized the quiz.

o If the user gave an answer, it validated whether it was A, B, or C, compared it to
the correct answer, and updated the score.

o If the quiz was complete, it calculated the percentage and gave personalized
feedback (like “Perfect! You’re an S3 expert!”).

 Session Attributes: I used attributes like quizActive, currentIndex, and score to
keep track of the quiz state across multiple turns. This way, the bot remembered which
question the user was on and how many they had answered correctly.

 ❓Helper Functions:

o start_quiz() initialized the quiz, set the score to 0, and presented the first
question.

o handle_quiz_answer() validated answers, gave feedback, advanced to the next
question, or ended the quiz with a final score.

o build_response() constructed the Lex response with the right message and
dialog action.

# ✨Key Highlights
 Structured Questions: All quiz content was stored in a Python list for easy management.

 State Management: Session attributes tracked progress and score.

 Validation: Only A, B, or C were accepted as valid answers.

 Feedback: Immediate feedback after each question, plus a final score with
encouragement.

 Error Handling: If the user gave invalid input, the bot prompted them to try again
without breaking the flow

5. Testing and Building the Bot
 After configuring everything, I clicked Build in the Lex console. Once the build finished,
I tested the bot using the test window.

 I tried sample utterances like “Start quiz” and “A” to see how the bot responded. I
inspected JSON interactions to confirm session attributes were tracked correctly. I also
tested edge cases, like invalid answers, and conducted user acceptance testing with real
users.

 This helped me refine the

## 📝My Takeaways
- I gained a better understanding of how chatbots are designed and how user input is processed to generate responses.
- I learned how to work with chatbot logic, including handling different conversation flows and edge cases.
- This project helped me improve my problem-solving and debugging skills while developing and testing features.
- I strengthened my ability to collaborate in a group setting, including sharing ideas, dividing tasks, and integrating code from different team members.
- I learned the importance of clear documentation and version control when working on a shared GitHub repository.

## Team Members & Roles
Lindokuhle.D - Reasearch & Documentation

Andrea. - Reasearch & Documentation

Unathi - Reasearch & Documentation

Lethabo - Deployment & Creation of the Chatbot
