# FIVE-STEP REQUEST FLOW
1. Request to Server
2. Request to Anthropic API
3. Model Precessing
4. Response to Server
5. Response to Client

## 1. REQUEST TO SERVER
 - Requesto to anthropic should not be made directly from client code.
 - API request requires a secret API KEY, which shouldn't be exposed to the client.
    - Exposing this key in client code creates a serious security vulnerability.
    - Anyone could extract the key and make unauthorized request.

## 2. REQUEST TO ANTHROPIC API
 - API key: Indetifies your request to anthropic.
 - Model: Name of the model to use (like "claude-opus-5-5").
 - Messages: List of "messages" containing the user's input text.
 - Max Tokens: Limit to how many "tokens" the model can generate.

## 3. MODEL PROCESSING
 - Tokenization: splitting user input into separate tokens.
 - Embedding: Each token gets converted into an embedding a long list of numbers that represents all possible meanings of that word. Think of embeddings as numerical definitions that capture semantic relationships.
    - Possible meanings for each "token" of user input.
 - Contextualization: Comparing the lists of numbers corresponding to each token to understand the context.
 - Generation: Response.
    - After selecting each word, Claude adds it to the sequence and repeats the entire process for the next word.
## 4. RESPONSE TO SERVER
 - Response structure
    - Message: The generated text
    - Usage: Count of input and output tokens
    - Stop Reason: Whi generation ended
## 5. RESPONSE TO CLIENT
 - User input > Request Anthropic SDK (Your Server) > Request Anthropic API > Response to Anthropic SDK (Your Server) > Response to client.
 - Helps:
    - Desing secure architectures that protect your API keys
    - Set appropriate token limits for your use case
    - Handle different stop reasons in your application logic
    - Debug issues by understanding where they might occur the pipeline
    





