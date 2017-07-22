# Messaging APIs

[![Build Status](https://travis-ci.org/Yoctol/messaging-apis.svg?branch=master)](https://travis-ci.org/Yoctol/messaging-apis)
[![coverage](https://codecov.io/gh/Yoctol/messaging-apis/branch/master/graph/badge.svg)](https://codecov.io/gh/Yoctol/messaging-apis)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Messaging APIs is a [mono repo](https://github.com/babel/babel/blob/master/doc/design/monorepo.md) which collects APIs needed for bot development.

It helps you build your bots using similar API for multiple platforms, e.g. Messenger, LINE. Learn once and make writing cross-platform bots easier.

![](https://user-images.githubusercontent.com/2382594/28054681-7c61882a-6648-11e7-8148-ce969230900e.png)

## Packages

| Package | Version | Platform |
|---------|---------|-------------|
| [`messaging-api-messenger`](/packages/messaging-api-messenger) | [![npm](https://img.shields.io/npm/v/messaging-api-messenger.svg?style=flat-square)](https://www.npmjs.com/package/messaging-api-messenger) | [Messenger](https://www.messenger.com/) |
| [`messaging-api-line`](/packages/messaging-api-line) | [![npm](https://img.shields.io/npm/v/messaging-api-line.svg?style=flat-square)](https://www.npmjs.com/package/messaging-api-line) | [LINE](https://line.me/) |
| [`messaging-api-slack`](/packages/messaging-api-slack) | [![npm](https://img.shields.io/npm/v/messaging-api-slack.svg?style=flat-square)](https://www.npmjs.com/package/messaging-api-slack) | [Slack](https://slack.com/) |
| [`messaging-api-telegram`](/packages/messaging-api-telegram) | [![npm](https://img.shields.io/npm/v/messaging-api-telegram.svg?style=flat-square)](https://www.npmjs.com/package/messaging-api-telegram) | [Telegram](https://telegram.org/) |

## Usage

### Messenger

Install `messaging-api-messenger` package from the registry:

```sh
npm i --save messaging-api-messenger
```
or
```sh
yarn add messaging-api-messenger
```

Then, create a `MessengerClient` to call Messenger APIs:

```js
import { MessengerClient } from 'messaging-api-messenger';

// get accessToken from facebook developers website
const client = MessengerClient.connect(accessToken);

client.sendText(userId, 'Hello World').then(() => {
  console.log('sent');
});



```

Check out [full API documentation](./packages/messaging-api-messenger/README.md) for more detail information.

### LINE

Install `messaging-api-line` package from the registry:

```sh
npm i --save messaging-api-line
```
or
```sh
yarn add messaging-api-line
```

Then, create a `LINEClient` to call LINE APIs:

```js
import { LINEClient } from 'messaging-api-line';

// get accessToken and channelSecret from LINE developers website
const client = LINEClient.connect(accessToken, channelSecret);

client.pushText(userId, 'Hello World').then(() => {
  console.log('pushed');
});



```

Check out [full API documentation](./packages/messaging-api-line/README.md) for more detail information.

### Slack

Install `messaging-api-slack` package from the registry:

```sh
npm i --save messaging-api-slack
```
or
```sh
yarn add messaging-api-slack
```

Then, create a `SlackClient` to call Slack APIs:

```js
import { SlackClient } from 'messaging-api-slack';

// get webhook URL by adding a Incoming Webhook integration to your team.
// https://my.slack.com/services/new/incoming-webhook/
const client = SlackClient.connect(
  'https://hooks.slack.com/services/XXXXXXXX/YYYYYYYY/zzzzzZZZZZ'
);

client.sendText('Hello World').then(() => {
  console.log('sent');
});



```

Check out [full API documentation](./packages/messaging-api-slack/README.md) for more detail information.

### Telegram

Install `messaging-api-telegram` package from the registry:

```sh
npm i --save messaging-api-telegram
```
or
```sh
yarn add messaging-api-telegram
```

Then, create a `TelegramClient` to call Telegram APIs:

```js
import { TelegramClient } from 'messaging-api-telegram';

// get accessToken from telegram [@BotFather](https://telegram.me/BotFather)
const client = TelegramClient.connect('12345678:AaBbCcDdwhatever');

client.sendMessage(chatId, 'Hello World').then(() => {
  console.log('sent');
});



```

Check out [full API documentation](./packages/messaging-api-telegram/README.md) for more detail information.

## Documentation

- [Messenger](./packages/messaging-api-messenger/README.md)
- [LINE](./packages/messaging-api-line/README.md)
- [Slack](./packages/messaging-api-slack/README.md)
- [Telegram](./packages/messaging-api-telegram/README.md)

## Change Log

Every release, along with the migration instructions, is documented on the [CHANGELOG.md](./CHANGELOG.md) file.

## License

MIT © [Yoctol](https://github.com/Yoctol/messaging-apis)
