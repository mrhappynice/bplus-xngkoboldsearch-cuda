# bplus🤷🏻‍♂️ XNGkoboldsearch-cuda
---
Start in a few seconds on runpod.io:
(https://console.runpod.io/deploy?template=iysy5dw0ms)

--- 
Private local search with SearXNG, Custom bplus-search app(search without MCP), and Koboldcpp to run any models in the single container. cuda

- run.sh:
```sh
docker run --name xngkoboldsearch-cuda-cont -d \
  -p 8080:8080 \
  -p 3001:3001 \
  -p 1234:1234 \
  --gpus all \
  -v "$PWD/config:/etc/searxng" \
  -v "$PWD/data:/var/cache/searxng" \
  -e INSTANCE_NAME="SearXNG" \
  -e BASE_URL="http://localhost:8080/" \
  -e SEARXNG_URL=http://127.0.0.1:8080 \
  -e AUTH_USERNAME= \
  -e AUTH_PASSWORD= \
  -e OPENAI_API_BASE=http://localhost:1234/v1 \
  -e LMSTUDIO_API_BASE="http://localhost:1234/v1" \
  -e OPENAI_API_KEY="sk-proj-xxxxx-x-x-x-xx" \
  -e OPENROUTER_API_KEY="sk-oxxxxr-xx-xxxx" \
  -e GOOGLE_API_KEY="xxxxx" \
  -e MODEL_URL="https://huggingface.co/unsloth/Qwen3-0.6B-GGUF/resolve/main/Qwen3-0.6B-Q8_0.gguf" \
  mrhappynice/bplus-xngkoboldsearch-cuda 


```

- add your keys and Koboldcpp/llama.cpp compatible gguf in the MODEL_URL e-var, from huggingface with the quant as shown

- using:
  - [Llama.cpp](https://github.com/ggml-org/llama.cpp/releases/tag/b6912)
  - [bplus-search](https://github.com/mrhappynice/bplus-search)
  - [SearXNG](https://github.com/searxng/searxng)
