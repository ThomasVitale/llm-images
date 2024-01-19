FROM --platform=$BUILDPLATFORM docker.io/ollama/ollama:latest

RUN bash -c '                             \
    ( ollama serve ) & serverpid="$!";    \
    sleep 5;                              \
    ollama pull llama2 &&                    \
    kill "$serverpid" &&                  \
    wait "$serverpid"                     \
'