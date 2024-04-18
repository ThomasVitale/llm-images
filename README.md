# OCI Images for Open-Source Large Language Models (LLMs)

Catalog of multi-architecture OCI images for popular free and/or open-source Large Language Models, built and published weekly.

## 🦙 Ollama

* `ghcr.io/thomasvitale/ollama-bakllava`
* `ghcr.io/thomasvitale/ollama-llama2`
* `ghcr.io/thomasvitale/ollama-llama3`
* `ghcr.io/thomasvitale/ollama-llava`
* `ghcr.io/thomasvitale/ollama-mistral`
* `ghcr.io/thomasvitale/ollama-orca-mini`
* `ghcr.io/thomasvitale/ollama-phi`

## 🔐 Signatures and Attestations

All OCI images published in this project are signed with [Sigstore](https://www.sigstore.dev).

Using the `cosign` CLI, you can display the supply chain security related artifacts for each image. Use the specific digest you'd like to verify.

```shell
cosign tree ghcr.io/thomasvitale/ollama-llama3
```

The result:

```shell
📦 Supply Chain Security Related artifacts for an image: ghcr.io/thomasvitale/ollama-llama3
└── 🔐 Signatures for an image tag: ghcr.io/thomasvitale/ollama-llama2:sha256-6838079fb6c6c0ea8c8b7e0c47a1bb365f839764b5480e01d8e0b0141d2817da.sig
   └── 🍒 sha256:c8c8b819ec15833b0ae8a4f64ad5f3e9fbc1bd175e91051290f33c2a707958da
```

You can verify the signature and its claims:

```shell
cosign verify \
   --certificate-identity-regexp https://github.com/ThomasVitale \
   --certificate-oidc-issuer https://token.actions.githubusercontent.com \
   ghcr.io/thomasvitale/ollama-llama3 | jq
```

## 🌟 Examples

These images are used for running LLMs in development and testing using Testcontainers or Docker Compose. You can find examples of usage in [Spring AI](https://github.com/ThomasVitale/llm-apps-java-spring-ai) and [LangChain4j](https://github.com/ThomasVitale/llm-apps-java-langchain4j).

## 🛡️&nbsp; Security

The security process for reporting vulnerabilities is described in [SECURITY.md](SECURITY.md).

## 🖊️&nbsp; License

This project is licensed under the **Apache License 2.0**. See [LICENSE](LICENSE) for more information.
