# streamlit-chatbot-app
Sample streamlit app that presents a chatbot experience to the user

1. Create your own API token by creating an account on https://huggingface.co/. Replace `os.environ['HUGGING_FACE_API_TOKEN']` in the code with your token or add a user level environment variable in Domino with key as `HUGGING_FACE_API_TOKEN` and value as the token.
2. Modify the `API_URL` to experiment with different models from the Hugging Face Library. The code is set to use the conversational `models/microsoft/DialoGPT-large` model by default.
3. `query_model_api_in_Domino` function depicts the outline for a generic model API hosted within Domino. Please create your own model and host it as an API in your Domino deployment by following the instructions [in this article](https://docs.dominodatalab.com/en/latest/user_guide/8dbc91/host-models-as-rest-apis/). Then add the details of your domino deployment, model id, model parameters in the function to send requests to your model.

# Deploying the Naive Bayes movie genre prediction model as a Model API
A simple naive bayes model trained to predict movie genres based on movie summary text has been provided in the `Model API` folder. Instead of deploying your own model, you can choose to deploy this model and use it for demonstration purposes. To deploy the model,
1. Place all the files in the `Model API` directory under `/mnt` in your project
2. Modify the paths to the `.pkl` files in the `api_nb.py` file according to where you place them in step 2
3. In your project, go to Publish > Model APIs > Create Model API
4. Give your model a nice name and click Next
5. The file that you'll invoke is `api_nb.py` and the function to invoke is `np_predict`
6. Leave all other settings as default and click Create Model

Once the model is deployed as an API, navigate to the Tester tab in the Model API that's running, paste the below content in the Request and hit Send. The tester tab is great for quickly testing if you Model API is running and providing a response.

`{
  "data": {
    "input_string": "Once upon a time, in a far away swamp, there lived an ogre named Shrek (Mike Myers) whose precious solitude is suddenly shattered by an invasion of annoying fairy tale characters. They were all banished from their kingdom by the evil Lord Farquaad (John Lithgow). Determined to save their home -- not to mention his -- Shrek cuts a deal with Farquaad and sets out to rescue Princess Fiona (Cameron Diaz) to be Farquaad's bride. Rescuing the Princess may be small compared to her deep, dark secret."
  }
}`

If all looks good, navigate to the `Python` tab and use the code from there to invoke your model via the `query_model_api_in_Domino` function in your Streamlit App!
