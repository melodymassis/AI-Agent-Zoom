Building a Zoom Chatbox:
AI model trained by Meta AI, serving as an interface for the conversational AI model LLaMA

Deployed in development using Ngrok

- Created an App in Zoom marketplace: https://developers.zoom.us/docs/team-chat-apps/create-chatbot/
- Used Cerebras Inference Library https://cloud.cerebras.ai/

Modified code to answer in both English and Spanish

Original Code:
const requestData = {
    model: 'llama3.1-8b',  // Specify which model to use
    messages: [
        { role: 'system', content: 'You are a helpful assistant.' }, // English default system message
        { role: 'user', content: payload.cmd }
    ],
    max_tokens: 500  // Limit the response length
};

Modified Code:

const requestData = {
    model: 'llama3.1-8b',  // Specify which model to use
    messages: [
        { role: 'system', content: 'You are a helpful assistant and should respond in Spanish.' }, // Spanish default system message
        { role: 'user', content: payload.cmd }
    ],
    max_tokens: 500  // Limit the response length
};
