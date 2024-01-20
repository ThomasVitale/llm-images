FROM docker.io/ollama/ollama:latest

RUN bash -c '                                  \
    ( ollama serve ) & serverpid="$!";         \
    sleep 5;                                   \
    ollama pull phi &&                         \
    kill "$serverpid" &&                       \
    wait "$serverpid"                          \
'
