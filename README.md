# Bot de Horóscopo para Telegram

Este é um bot simples para o Telegram, construído em Python, que fornece o horóscopo diário para qualquer signo do zodíaco. O bot interage com o usuário de forma conversacional para obter o signo e a data desejada.

## 🌟 Funcionalidades

- **Mensagem de Boas-Vindas**: Responde aos comandos `/start` e `/hello` com uma saudação amigável.
- **Busca de Horóscopo**: Através do comando `/horoscope`, o bot guia o usuário para obter o horóscopo.
- **Fluxo Conversacional**: Pergunta primeiro pelo signo do zodíaco e depois pelo dia (hoje, amanhã, ontem ou uma data específica).
- **Função de Eco**: Repete qualquer mensagem que não seja um comando conhecido, útil para testes.
- **Integração com API Externa**: Utiliza uma função auxiliar `get_daily_horoscope` (presumivelmente de uma API) para buscar os dados do horóscopo.

---

## 🚀 Comandos do Bot

- `/start` ou `/hello`: Inicia a interação com o bot e recebe uma mensagem de boas-vindas.
- `/horoscope`: Inicia o processo para obter o horóscopo. O bot irá solicitar as informações necessárias em etapas.

---

## 📋 Pré-requisitos

Para executar este bot, você precisará de:

- Python 3.x
- Uma conta no Telegram e um token de bot. Você pode obter um token falando com o [@BotFather](https://t.me/BotFather) no Telegram.
- As bibliotecas Python listadas no arquivo `requirements.txt`.

---

## ⚙️ Configuração e Instalação

1.  **Clone o repositório:**
    ```bash
    git clone https://github.com/PittViic/bot-horoscope.git
    cd seu-repositorio
    ```

2.  **Crie e ative um ambiente virtual (recomendado):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # No Windows, use `venv\Scripts\activate`
    ```

3.  **Instale as dependências:**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Configure o Token do Bot:**
    Você precisa definir o seu token do Telegram como uma variável de ambiente.

    **No Linux/macOS:**
    ```bash
    export BOT_TOKEN="SEU_TOKEN_AQUI"
    ```

    **No Windows (PowerShell):**
    ```powershell
    $env:BOT_TOKEN="SEU_TOKEN_AQUI"
    ```

5.  **Módulo de Utilitários (`utils.py`):**
    Este bot depende de um arquivo `utils.py` que contém a função `get_daily_horoscope(sign, day)`. Certifique-se de que este arquivo esteja no mesmo diretório e que a função esteja implementada corretamente para se conectar à API de horóscopo de sua escolha.

    **Exemplo de estrutura para `utils.py`:**
    ```python
    import requests

    def get_daily_horoscope(sign: str, day: str) -> dict:
        """Busca o horóscopo de uma API externa."""
        # Exemplo de chamada de API (substitua pela sua API real)
        # url = f"[https://api.example.com/horoscope?sign=](https://api.example.com/horoscope?sign=){sign}&day={day}"
        # response = requests.get(url)
        # return response.json()

        # Exemplo de dados mockados
        return {
            "data": {
                "date": day,
                "horoscope_data": f"Este é o horóscopo de hoje para {sign}..."
            }
        }
    ```

---

## ▶️ Como Executar o Bot

Após a configuração, execute o seguinte comando no seu terminal para iniciar o bot:

```bash
python main.py
```

O bot começará a rodar e a escutar por mensagens no Telegram.

---

## 📦 Dependências

As dependências do projeto estão listadas abaixo. Você pode instalá-las usando `pip`.

**`requirements.txt`:**
```
pyTelegramBotAPI
```
