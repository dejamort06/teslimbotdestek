const { createBot } = require('@venom-bot/core');
const { handleMessage } = require('./messageHandler');
const ayarlar = require('./ayarlar.json');

createBot({
  session: 'bot',
  disableWelcome: true
}).then((client) => {
  client.onMessage((message) => {
    handleMessage(client, message, ayarlar);
  });
});
