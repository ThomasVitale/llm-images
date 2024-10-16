# OCI Images for Open-Source Large Language Models (LLMs)

![Release Workflow](https://github.com/ThomasVitale/llm-images/actions/workflows/commit-stage.yml/badge.svg)
[![The SLSA Level 3 badge](https://slsa.dev/images/gh-badge-level3.svg)](https://slsa.dev/spec/v1.0/levels)

Catalog of multi-architecture OCI images for popular free and/or open-source Large Language Models, built and published weekly.

## 🦙 Ollama

Images are built weekly based on the latest version of [Ollama](https://ollama.com) and the specific models. They are published with three tags: `latest`, Git commit sha, and timestamp.

* `ghcr.io/thomasvitale/ollama-aya`
* `ghcr.io/thomasvitale/ollama-gemma2`
* `ghcr.io/thomasvitale/ollama-llama3-2`
* `ghcr.io/thomasvitale/ollama-llava`
* `ghcr.io/thomasvitale/ollama-mistral`
* `ghcr.io/thomasvitale/ollama-moondream`
* `ghcr.io/thomasvitale/ollama-nomic-embed-text`
* `ghcr.io/thomasvitale/ollama-phi3-5`
* `ghcr.io/thomasvitale/ollama-qwen2-5`

The following images are still available, but they will not receive further updates.

* `ghcr.io/thomasvitale/ollama-bakllava`
* `ghcr.io/thomasvitale/ollama-llama2`
* `ghcr.io/thomasvitale/ollama-llama3`
* `ghcr.io/thomasvitale/ollama-llama3-1`
* `ghcr.io/thomasvitale/ollama-llava-phi3`
* `ghcr.io/thomasvitale/ollama-mistral-nemo`
* `ghcr.io/thomasvitale/ollama-mxbai-embed-large`
* `ghcr.io/thomasvitale/ollama-orca-mini`
* `ghcr.io/thomasvitale/ollama-phi`
* `ghcr.io/thomasvitale/ollama-phi3`

## 🔐 Signatures and Attestations

All OCI images published in this project are signed with [Sigstore](https://www.sigstore.dev).

Using the `cosign` CLI, you can display the supply chain security related artifacts for each image. Use the specific digest you'd like to verify.

```shell
cosign tree ghcr.io/thomasvitale/ollama-mistral
```

The result:

```shell
📦 Supply Chain Security Related artifacts for an image: ghcr.io/thomasvitale/ollama-mistral
└── 💾 Attestations for an image tag: ghcr.io/thomasvitale/ollama-mistral:sha256-38e80d235799aaa8d1bd98733c8b24ae0afb43620391205bb990d4513ee9e751.att
   └── 🍒 sha256:89e502711643e116436fc73ba50345e414f73e90cde7c6d0cc29a4b81a7ffce4
└── 🔐 Signatures for an image tag: ghcr.io/thomasvitale/ollama-mistral:sha256-38e80d235799aaa8d1bd98733c8b24ae0afb43620391205bb990d4513ee9e751.sig
   └── 🍒 sha256:951e0e299a6585ae117ca31f4df7edb20907391df228d52d624cb552a95c71d4
```

You can verify the signature and its claims:

```shell
cosign verify \
   --certificate-identity-regexp https://github.com/ThomasVitale \
   --certificate-oidc-issuer https://token.actions.githubusercontent.com \
   ghcr.io/thomasvitale/ollama-mistral | jq
```

You can also verify the SLSA attestation as follows:

```shell
cosign verify-attestation --type slsaprovenance \
   --certificate-identity-regexp https://github.com/slsa-framework \
   --certificate-oidc-issuer https://token.actions.githubusercontent.com \
   ghcr.io/thomasvitale/ollama-mistral | jq .payload -r | base64 --decode | jq
```

## 🌟 Examples

These images are used for running LLMs in development and testing using [Testcontainers](https://testcontainers.com/modules/ollama/) or Docker Compose. You can find examples of usage in [Spring AI](https://github.com/ThomasVitale/llm-apps-java-spring-ai) and [LangChain4j](https://github.com/ThomasVitale/llm-apps-java-langchain4j).

## 🛡️&nbsp; Security

The security process for reporting vulnerabilities is described in [SECURITY.md](SECURITY.md).

## 🖊️&nbsp; License

This project is licensed under the **Apache License 2.0**. See [LICENSE](LICENSE) for more information.
[Ollama](https://github.com/ollama/ollama/blob/main/LICENSE) is licensed under the MIT License.
Each model is licensed individually. You can find more information in the Ollama [model library](https://ollama.com/library).
