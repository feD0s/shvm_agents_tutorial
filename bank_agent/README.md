Пример агента для LangGraph в виде микросервиса

Для запуска:

    Изучите документацию Doc: https://langchain-ai.github.io/langgraph/tutorials/langgraph-platform/local-server/
    Установите langgraph-cli: pip install --upgrade "langgraph-cli[inmem]" (на маке нужет rust!)
    Создайте venv
    Установите зависимости (см. agentic_reasoning.ipynb)
    Переименуйте .env.example в .env и настройте креды
    Запустите через langgraph dev langgraph dev
    Можно обратиться через curl:

curl -s --request POST \
    --url "http://localhost:2024/runs/stream" \
    --header 'Content-Type: application/json' \
    --data "{
        \"assistant_id\": \"agent\",
        \"input\": {
            \"messages\": [
                {
                    \"role\": \"human\",
                    \"content\": \"Какие у меня есть банковские карты?\"
                }
            ]
        },
        \"stream_mode\": \"updates\"
    }" 

