# A Telegram ChatGPT bot

Deploy this function on flows.network, and you will get a Telegram bot that uses ChatGPT to respond to every question in your Telegram DM or channel/group automatically.

<img width="1151" alt="image" src="https://user-images.githubusercontent.com/45785633/226554378-0ea64870-186d-4449-9ae8-d84a2bedf8f6.png">

The example in the above image is to leverage ChatGPT to generate code comments.

## Prerequisite

* You will need an [OpenAI API key](https://openai.com/blog/openai-api). If you do not already have one, [sign up here](https://platform.openai.com/signup).

* You also need a Telegram token to access the HTTP API. If you don't already have one, go to Telegram to get a telegram bot token from [@botfather](https://telegram.me/BotFather).



## Deploy a ChatGPT Telegram bot 

To install the ChatGPT Telegram App, we will use [flows.network](https://flows.network/), a serverless platform that makes deploying your own app quick and easy in just three steps.

### Prepare the code: fork this repo

Fork [this repo](https://github.com/flows-network/telegram-gpt) and go to flows.network to deploy your function.

### Deploy the code on flow.network

1. Sign up for an account for deploying flows on flows.network. It's free.

2. Click on the "Create a Flow" button to start deploying the ChatGPT GitHub APP

3. Authenticate the flows.network to access the `telegram-gpt` repo you just forked.
![image](https://user-images.githubusercontent.com/45785633/226558160-7a319520-2212-41e4-b40e-43ca5f8d5712.png)

4. Click the Advanced test to see more settings. Here we need to use Environment Variables to pass the Telegram token and OpenAI API key name. 
* `telegram_token`: Fill in the token you received from Fatherbot.
* `openai_key_name`: Fill in the name you want to name your OpenAI key.

![image](https://user-images.githubusercontent.com/45785633/226562489-ff140061-d1e4-44ab-8cc9-369983cb016d.png)

5. At last, click the Deploy button to deploy your function.

## Configure SaaS integrations

After that, the flows.network will direct you to configure the SaaS integration required by your flow. Since we have configured Telegram in the above step, OpenAI is the only SaaS we need to configure here. 

![image](https://user-images.githubusercontent.com/45785633/226564674-902933b5-8ff3-4724-93e3-2b2f67dc0b9a.png)

Click the "Connect/+ Add new authentication" button to authenticate your OpenAI account. You'll be redirected to a new page where you can copy and paste your OpenAI API key and then name the key. Note that the name you enter here should be the same as the name in the environment variables.

<img width="758" alt="image" src="https://user-images.githubusercontent.com/45785633/222973214-ecd052dc-72c2-4711-90ec-db1ec9d5f24e.png">

## Give it a try. 

Click the Check button to see your flow details. As soon as the flow function's status becomes `ready` and the flow's status becomes `running`, the Telegram ChatGPT App goes live. Go ahead and chat with ChatGPT by sending a message on your Telegram! You can also invite this bot to your channel/group.

> [flows.network](https://flows.network/) is still in its early stages. We would love to hear your feedback!

## Others

If you want to build locally, make sure you have installed Rust and added `wasm32-wasi` traget.

```
cargo build --target wasm32-wasi --release
```
