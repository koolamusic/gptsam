# GPTSAM <!-- omit in toc -->

A CLI Wrapper on top of the [ChatGPT](https://openai.com/blog/chatgpt/) API.

> This CLI Package is based off the Node.js client for the official [ChatGPT](https://openai.com/blog/chatgpt/) API.

Learn more about the 
- OpenAI [ChatGPT](https://openai.com/blog/chatgpt/).
- ChatGPT API [chatgpt-api](https://github.com/transitive-bullshit/chatgpt-api)

## Intro

This package is a Node.js wrapper around [ChatGPT](https://openai.com/blog/chatgpt) by [OpenAI](https://openai.com). TS batteries included. ✨

<p align="center">
  <img alt="Example usage" src="/media/demo.gif">
</p>

## Usage


Sign up for an [OpenAI API key](https://platform.openai.com/overview) and setup the CLI:
  
```bash
gptsam setup --token <your-openai-token>
```


You can also use your command line `export` functionality to store it in your environment.

```bash
export OPENAI_API_KEY="sk-TODO"
npx gptsam "your prompt here"
```

By default, the response is streamed to stdout, the results are stored in a local config file, and every invocation starts a new conversation. You can use `-c` to continue the previous conversation and `--no-stream` to disable streaming.

```sh
Usage:
  $ gptsam <prompt>

Commands:
  <prompt>  Ask ChatGPT a question
  rm-cache  Clears the local message cache
  ls-cache  Prints the local message cache path

For more info, run any command with the `--help` flag:
  $ gptsam --help
  $ gptsam setup --help
  $ gptsam rm-cache --help
  $ gptsam ls-cache --help

Options:
  -c, --continue          Continue last conversation (default: false)
  -d, --debug             Enables debug logging (default: false)
  -s, --stream            Streams the response (default: true)
  -s, --store             Enables the local message cache (default: true)
  -t, --timeout           Timeout in milliseconds
  -k, --apiKey            OpenAI API key
  -n, --conversationName  Unique name for the conversation
  -h, --help              Display this message
  -v, --version           Display version number
```

## Install

```bash
npm i -g gptsam
```

Make sure you're using `node >= 18` so `fetch` is available (or `node >= 14` if you install a [fetch polyfill](https://github.com/developit/unfetch#usage-as-a-polyfill)).

## Caveats

This project uses the [`ChatGPTAPI`](https://github.com/transitive-bullshit/chatgpt-api) class which relies on the `gpt-3.5-turbo-0301` model with the official OpenAI chat completions API (official, robust approach, but it's not free). You can override the model, completion params, and system message to fully customize your assistant.

## Compatibility

- This package is ESM-only.
- This package supports `node >= 14`.
- This module assumes that `fetch` is installed.
  - In `node >= 18`, it's installed by default.
  - In `node < 18`, you need to install a polyfill like `unfetch/polyfill` ([guide](https://github.com/developit/unfetch#usage-as-a-polyfill)) or `isomorphic-fetch` ([guide](https://github.com/matthew-andrews/isomorphic-fetch#readme)).
- If you want to build a website using `chatgpt`, we recommend using it only from your backend API

## Credits

- Huge thanks to [Travis Fischer](https://transitivebullsh.it) for creating the Nodejs ChatGPT API [@waylaidwanderer](https://github.com/waylaidwanderer), [@abacaj](https://github.com/abacaj), [@wong2](https://github.com/wong2), [@simon300000](https://github.com/simon300000), [@RomanHotsiy](https://github.com/RomanHotsiy), [@ElijahPepe](https://github.com/ElijahPepe), and all the other contributors 💪
- The original browser version was inspired by this [Go module](https://github.com/danielgross/whatsapp-gpt) by [Daniel Gross](https://github.com/danielgross)
- [OpenAI](https://openai.com) for creating [ChatGPT](https://openai.com/blog/chatgpt/) 🔥

## License

MIT © [Andrew Miracle](https://andrewmiracle.com)