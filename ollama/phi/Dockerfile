FROM --platform=$BUILDPLATFORM docker.io/ollama/ollama:latest

ENV OLLAMA_HOST 0.0.0.0

EXPOSE 11434

RUN bash -c '                             \
    ( ollama serve ) & serverpid="$!";    \
    sleep 5;                              \
    ollama pull phi &&                    \
    kill "$serverpid" &&                  \
    wait "$serverpid"                     \
'
