<!-- markdownlint-disable MD030 -->

# VertBuild Embed
Install:

```bash
yarn install
```

Dev:

```bash
yarn dev
```

Build:

```bash
yarn build
```

## Embed in HTML

### PopUp

```html
<script type="module">
  import Chatbot from 'https://cdn.jsdelivr.net/npm/vertbuild-embed/dist/web.js';
  Chatbot.init({
    chatflowid: '<chatflowid>',
    apiHost: 'http://localhost:3000',
  });
</script>
```

### FullPage

```html
<script type="module">
  import Chatbot from './web.js';
  Chatbot.initFull({
    chatflowid: '<chatflowid>',
    apiHost: 'http://localhost:3000',
  });
</script>
<vertbuild-fullchatbot></vertbuild-fullchatbot>
```

To enable full screen, add `margin: 0` to <code>body</code> style, and confirm you don't set height and width

```html
<body style="margin: 0">
  <script type="module">
    import Chatbot from './web.js';
    Chatbot.initFull({
      chatflowid: '<chatflowid>',
      apiHost: 'http://localhost:3000',
      theme: {
        chatWindow: {
          // height: 700, don't set height
          // width: 400, don't set width
        },
      },
    });
  </script>
</body>
```

## Configuration

You can also customize chatbot with different configuration

```html
<script type="module">
  import Chatbot from 'https://cdn.jsdelivr.net/npm/vertbuild-embed/dist/web.js';
  Chatbot.init({
    chatflowid: '91e9c803-5169-4db9-8207-3c0915d71c5f',
    apiHost: 'http://localhost:3000',
    chatflowConfig: {
      // topK: 2
    },
    theme: {
      button: {
        backgroundColor: '#3B81F6',
        right: 20,
        bottom: 20,
        size: 'medium',
        iconColor: 'white',
        customIconSrc:
          'https://raw.githubusercontent.com/walkxcode/dashboard-icons/main/svg/google-messages.svg',
      },
      chatWindow: {
        welcomeMessage: 'Hello! This is custom welcome message',
        backgroundColor: '#ffffff',
        height: 700,
        width: 400,
        fontSize: 16,
        poweredByTextColor: '#303235',
        botMessage: {
          backgroundColor: '#f7f8ff',
          textColor: '#303235',
          showAvatar: true,
          avatarSrc:
            'https://raw.githubusercontent.com/zahidkhawaja/langchain-chat-nextjs/main/public/parroticon.png',
        },
        userMessage: {
          backgroundColor: '#3B81F6',
          textColor: '#ffffff',
          showAvatar: true,
          avatarSrc:
            'https://raw.githubusercontent.com/zahidkhawaja/langchain-chat-nextjs/main/public/usericon.png',
        },
        textInput: {
          placeholder: 'Type your question',
          backgroundColor: '#ffffff',
          textColor: '#303235',
          sendButtonColor: '#3B81F6',
        },
      },
    },
  });
</script>
```

