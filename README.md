
# EDS Channel Tracker Worker 



## 🛠 A Cloudflare Worker: Slack & Teams API Proxy

This Cloudflare Worker acts as a backend API layer for Slack (and soon Microsoft Teams), handling authenticated requests and simplifying frontend integration.



## 📁 Project Structure

```text
worker/
├── index.js              # Entry point: handles fetch, CORS, and delegates to router
├── api/
│   ├── router.js         # Routes incoming requests to Slack or Teams handlers
│   ├── slack.js          # Slack-specific API logic (channels, messages, users)
├── utils/
│   ├── cors.js           # CORS response headers
│   ├── response.js       # jsonResponse, errorResponse, API error handling
│   └── common.js         # Utility functions (e.g. isHumanMessage)
```


## 📦 Current API Endpoints

### Slack

- `GET /slack/channels?channelName=&description=`
- `GET /slack/messageStats?channelId=`
- `GET /slack/members?channelId=`
- `GET /slack/user/info?userId=`


## ⚙️ Environment Variables

Configured in `wrangler.toml`:

- `SLACK_BOT_KEY`
- `SLACK_USER_KEY`
