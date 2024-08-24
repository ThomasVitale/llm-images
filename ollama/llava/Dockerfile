FROM docker.io/ollama/ollama:latest

ENV OLLAMA_NUM_PARALLEL=1

RUN /bin/sh -c "/bin/ollama serve & sleep 1 && ollama pull llava"
