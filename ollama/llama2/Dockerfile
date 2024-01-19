FROM --platform=$BUILDPLATFORM docker.io/ollama/ollama:latest
RUN /bin/sh -c "/bin/ollama serve & sleep 1 && ollama pull llama2"

EXPOSE 11434

ENTRYPOINT ["/bin/ollama"]
CMD ["serve"]