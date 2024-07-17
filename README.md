Open AI:

URL: https://openaineb2.openai.azure.com
Key: eaced5fcd8b144fab78ae0a297765377
Region: eastus
Deployment Name: Gpt-35
api-version: 2024-02-15-preview

# Workshop Semantic Kernel

## Exercise 1 - Chat
We will first start with a basic chat, and then evolve it to a more complex chat.

### A. Single message
 - [ ] Print hardcoded answer to console
 - [ ] Read the user input from console instead of hard coding it

<details><summary>Hint</summary>
Configure Kernel 

```csharp
var kernelBuilder = Kernel.CreateBuilder();
var config = new { modelID = "gpt-4", azureEndpoint = "", apiKey = "….." };
kernelBuilder.AddAzureOpenAIChatCompletion(config.modelID, config.azureEndpoint,config.apiKey);
var kernel = kernelBuilder.Build();
```
</details>
<details>
<summary>Hint 2</summary>
Invoke Service

```csharp
var chatService = kernel.GetRequiredService<IChatCompletionService>();
var chatResponse = await chatService.GetChatMessageContentAsync("Hi! How are you?");
Console.WriteLine(chatResponse);
```
</details>

 ### B. Full back and forth chat
 - [ ] Now that we can chat, let's allow for us to keep asking until we kill our app!
    

### C. Remember me!
 - [ ] Add a history to the chat so the model remembers what we talked about!
<details>
<summary>Hint</summary>
Keep array of messages to pass to call

</details>


### D. Bonus - steaming chat
 If wou would like to get that delayed output feel, you can
 use the GetStreamChatMessageContentAsync Method:

### E. Bonus - Plugin
 - [ ] Create a plugin get Chuck Norris jokes, pokemon, or any other API you like.

### F. Bonus - RAG
 - [ ] Initialize your light plugin with some data
<details>
<summary>Hint</summary>

[URL Hint](https://learn.microsoft.com/en-us/semantic-kernel/get-started/quick-start-guide?pivots=programming-language-csharp#6-add-plugins)

</details>
