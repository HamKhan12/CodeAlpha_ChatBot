# CodeAlpha_ChatBot

from nltk.chat.util import Chat, reflections

# Define the pairs of patterns and responses
patterns_responses = [
    (r'hi|hello|hey', ['Hello!', 'Hi there!', 'Hey!']),
    (r'how are you', ['I am fine, thank you!', 'I am good. How about you?', 'Doing well, thanks!']),
    (r'what is your name', ['I am a chatbot created by OpenAI.', 'You can call me Chatbot.']),
    (r'how can you help me', ['I can answer your questions and have a chat with you!', 'I am here to chat and provide information.']),
    (r'bye|goodbye', ['Goodbye!', 'See you later!', 'Have a great day!']),
]

# Create a chatbot
chatbot = Chat(patterns_responses, reflections)

# Function to start the chatbot
def start_chat():
    print("Hello! I am your chatbot. Type 'bye' to exit.")
    
    while True:
        user_input = input("You: ")
        
        # Exit the chat loop if the user says 'bye'
        if user_input.lower() in ['bye', 'goodbye']:
            print("Chatbot: Goodbye!")
            break
        
        # Get the chatbot's response
        response = chatbot.respond(user_input)
        
        # If no response is found, provide a default response
        if response:
            print(f"Chatbot: {response}")
        else:
            print("Chatbot: Sorry, I don't understand that.")

# Start the chatbot
if __name__ == "__main__":
    start_chat()
