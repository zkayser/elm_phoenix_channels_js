# Elm Phoenix Channels JS Client

This package is intended to be used in tandem with [this Elm Phoenix Channels client](https://github.com/zkayser/elm_phoenix_channels).

### Setup

Install from npm:

```bash
npm install elm_phoenix_channels
```

Then setup your JS code as follows:

```javascript
import { Socket } from 'phoenix';
import { ElmPhoenixChannels } from 'elm_phoenix_channels';

// Initialize with your Elm App:
const ELM_DIV = document.getElementById("elm-div");
const elmApp = Elm.Main.init(ELM_DIV);
new ElmPhoenixChannels(Socket, elmApp.ports);
```

Instantiating a new instance of ElmPhoenixChannels and passing in the ports from you're Elm app with the caveat that `ElmPhoenixChannels` is expecting your ports to have two ports defined: `fromPhoenix` and `toPhoenix`. More information can be found in the README for the [Elm repo](https://github.com/zkayser/elm_phoenix_channels), but essentially, `fromPhoenix` will return a `Sub msg` in your Elm app while `toPhoenix` will return a `Cmd msg`.