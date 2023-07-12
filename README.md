# streamlit-chatbot-app
Sample streamlit app that presents a chatbot experience to the user

1. Create your own API token by creating an account on https://huggingface.co/. Replace `os.environ['HUGGING_FACE_API_TOKEN']` in the code with your token or add a user level environment variable in Domino with key as `HUGGING_FACE_API_TOKEN` and value as the token.
2. Modify the `API_URL` to experiment with different models from the Hugging Face Library. The code is set to use the conversational `models/microsoft/DialoGPT-large` model by default.
3. `query_model_api_in_Domino` function depicts the outline for a generic model API hosted within Domino. Please create your own model and host it as an API in your Domino deployment by following the instructions [in this article]https://docs.dominodatalab.com/en/latest/user_guide/8dbc91/host-models-as-rest-apis/. Then add the details of your domino deployment, model id, model parameters in the function to send requests to your model.
