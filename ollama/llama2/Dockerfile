FROM --platform=$BUILDPLATFORM docker.io/ollama/ollama:latest

RUN ollama serve & sleep 10 && echo "Pulling model..." && ollama pull llama2

EXPOSE 11434

CMD ["serve"]