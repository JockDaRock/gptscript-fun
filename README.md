# Testing GPTScript out and having fun with some usecases.

> This is my repository for having some fun with GPTScript https://github.com/gptscript-ai/gptscript. I have been using this and I like how easy it is to use. Look for more updated examples as time goes on.

> My first gptscript is a modification of one of the examples from the gptscript repo. I modified it and the instructions to make it more user friendly for your dev environment. I also modified it to reduce clutter, utilize the system it is running on better, not install global dependencies, cleanup easier, etc. Basically it is almost full autopilot for getting your environment up and running... assuming you have the Requirements installed.

> Other notes: as mention in the requirements below, you need access to the OpenAI chatgpt AI and gpt4-turbo model, this requires you to pay. I have not tried out other models, so that is a bummer, I am looking to correct this soon. Basically gptscript takes advantage of the agent tools and functions parts of the gpt API from OpenAI.

> pywebapp.gpt is based on this original script I made modifications from... https://github.com/gptscript-ai/gptscript/blob/main/examples/hacker-news-headlines.gpt

## Requirements

1. GPTScript, duh... install instructions found here https://github.com/gptscript-ai/gptscript#quick-start
2. Install mongosh https://www.mongodb.com/docs/mongodb-shell/install/
3. Install and have Docker running so gptscript can start a mongo database for you. I use Rancher Desktop for this, but Docker Desktop or if you are on a Linux distribution OS just docker is fine.
4. A recent version of Python3 would be helpful
5. OpenAI ChatGPT API using gpt4-turbo model, it is the default model.

## Devices it has been tested on
* Mac Intel i9 64GB RAM using iterm2 as terminal
* Windows 11 AMD 32 GB RAM using WSL2 Ubuntu as terminal
* Mac M1 16 GB RAM using standard mac terminal

## Instructions on use

If you haven't already done so, git clone this repo and change directories into the folder.

```shell
git clone https://github.com/JockDaRock/gptscript-fun && cd gptscript-fun
```

Copy env.template file to .env to store our environment variables.

```shell
cp env.template .env
```

Edit the newly created .env file by adding in your API key for OpenAI

```
OPENAI_API_KEY=<some-api-key>
```

I would checkout the gptscript to make sure you agree with what is in it, you know because it will be executing commands on your computer... or just let it rip!

Now, run the command below to have your API key and other variables to be sourced as environment variables for gptscript to use.


```shell
env $(cat .env | xargs) gptscript pywebapp.gpt
```

This is a good point to checkout what is created and glance over the code that gptscript created for you. You can use this as a template if you want to create other python applications or just use it as is.

Now change directories to the newly created headline directory and then run the start.sh script to get the python program running.

```shell
cd headline && ./start.sh
```

Visit http://127.0.0.1:5000 or http://localhost:5000 in your browser.

Hit ctrl-c on your keyboard to exit the python app when you are ready.

Congrats you did it!!! Or the AI did it!!! whatever...

You could further automate the gptscript to do all of the starting everything for you so you don't have to follow the instructions, but that is for you to do ;).

## Cleanup

In your terminal in the gptscript-fun directory, run the following command cleanup your directory.

```shell
./gpt_cleanup.sh
```

