# Energy Savings Chatbot Example


## Building and Publishing the Chatbot Example

1. Clone this git repository:

```bash
cd ~   # or wherever you want
git clone https://github.com/iportilla/leeds-midterm.git
cd ~/leeds-midterm
```

2. Build the docker image:

```bash
make build
```

For example, when using the default values provided in this demo [hnz.json](https://raw.githubusercontent.com/jiportilla/Edge-Chatbot/master/horizon/hzn.json) configuration file:

```bash
docker build -t iportilla/chatbot_amd64:1.0.0 -f ./Dockerfile.amd64 .
```
