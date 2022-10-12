# Energy Savings Chatbot Example


## Building and Publishing the Chatbot Example

1. Clone this git repository:

```bash
cd ~   # or wherever you want
git clone https://github.com/iportilla/leeds-midterm.git
cd ~/leeds-midterm
```

2. Update the index.html page with your chatbot details:

```bash
nano (or vi) public-html/index.html
```

For example:

```script
<script>
  window.watsonAssistantChatOptions = {
    integrationID: "08642bc1-7afe-404a-b41b-77ab7a2c01e0", // The ID of this integration.
    region: "us-south", // The region your integration is hosted in.
    serviceInstanceID: "ede5a589-6df7-4928-9eeb-7dd8d859b216", // The ID of your service instance.
    onLoad: function(instance) { instance.render(); }
  };
  setTimeout(function(){
    const t=document.createElement('script');
    t.src="https://web-chat.global.assistant.watson.appdomain.cloud/versions/" + (window.watsonAssistantChatOptions.clientVersion || 'latest') + "/WatsonAssistantChatEntry.js";
    document.head.appendChild(t);
  });
</script>
```

3. Build the docker image:

```bash
make
```

4. To stop and clean Docker image

```bash
make stop
make clean
```

For example, when using the default values provided in this demo [hnz.json](https://raw.githubusercontent.com/jiportilla/Edge-Chatbot/master/horizon/hzn.json) configuration file:

```bash
docker build -t iportilla/chatbot_amd64:1.0.0 -f ./Dockerfile.amd64 .
```
