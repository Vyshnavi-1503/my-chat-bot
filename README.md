# Common Thread

A responsive, no-build clothing-storefront demo with product filtering, a saved shopping bag, an email sign-up demo, and a product-aware website assistant that can also answer ordinary non-shopping questions. The assistant runs against a local Ollama installation; it does not use an external AI API.

## Requirements

- Ruby and WEBrick (included with Ruby versions that ship WEBrick; Ruby 3 users can add it with `gem install webrick`).
- Ollama, running locally, with `llama3.2:latest`, `qwen2.5:3b`, or `qwen2.5:7b` pulled.
- An internet connection to load the sample product photographs and optional Google Fonts.

## Run locally

```sh
ruby server.rb
```

Open [http://localhost:3000](http://localhost:3000). The server discovers which of the three supported models are installed and lets you switch models in the chat window; `llama3.2:latest` is the default when available.

```sh
# Choose a different port or Ollama host if needed.
PORT=8080 OLLAMA_URL=http://localhost:11434 ruby server.rb
```

The server binds to `127.0.0.1` by default. To make the site available to other devices on a trusted local network, set `HOST=0.0.0.0` and make sure the machine's firewall and Ollama access are configured appropriately. In a deployment, run the backend on the same machine or network as Ollama and configure `OLLAMA_URL` to the Ollama server's reachable address.

## Store configuration

This is a front-end storefront sample. Product names, prices, photos, and categories are defined in `app.js`; the matching chatbot catalog and store details are in `server.rb`. Checkout displays a demo confirmation rather than collecting payment, and newsletter sign-up does not send email. Set your real store details and connect a payment and mailing-list provider before accepting orders.
