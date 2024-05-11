# Chatbot de RPG Medieval com Google AI Studio

Este projeto é um chatbot interativo de RPG medieval que utiliza a API do Google para gerar diálogos dinâmicos e imersivos. O chatbot simula a interação com NPCs (personagens não jogáveis) em uma cidade medieval, permitindo que o mestre monte dialogos melhores, e que o jogador converse com um mercador, um taverneiro ou um soldado.

## Objetivos:

* **Criar uma experiência de RPG textual:** Permitir que os jogadores interajam com um mundo medieval de fantasia através de texto.
* **Gerar diálogos realistas e contextuais:**  Utilizar a API do Google Gemini para criar diálogos que se adaptam ao contexto da conversa e às ações do jogador.
* **Simular diferentes personalidades:** Criar NPCs com personalidades distintas e que respondam de acordo com seus papéis no mundo do jogo.
* **Integrar elementos de RPG:**  Incluir elementos de RPG, como características de itens e anedotas regionais, para tornar a experiência mais imersiva.
* **Fornecer uma base para expansão:**  Criar uma estrutura flexível que possa ser expandida com mais NPCs, cidades, itens e funcionalidades.

## Estrutura do Código:

O código é estruturado da seguinte forma:

1. **Configuração da API:** Importação das bibliotecas necessárias e configuração da API do Google Gemini.
2. **Função `gerar_resposta_ia`:** 
    * Constrói o prompt para o modelo de linguagem, incluindo o histórico da conversa, a persona do NPC e a instrução para incluir características de itens quando necessário.
    * Envia o prompt para o modelo `gemini-1.0-pro` através da função `chat.send_message()`.
    * Adiciona uma anedota aleatória à resposta, se a persona for "taverneiro medieval".
    * Retorna a resposta formatada em verde.
3. **Loop Principal:**
    * Solicita o nome do jogador e a cidade inicial.
    * Apresenta um menu de opções para interagir com os NPCs ou trocar de cidade.
    * Gerencia o loop de interação com o NPC selecionado.
    * Permite que o jogador saia da conversa com o NPC digitando "SAIR".

## Justificativa para as Escolhas de Design:

* **Geração de Anedotas Aleatórias:** A aleatoriedade das anedotas do taverneiro adiciona variedade e imprevisibilidade à experiência do jogo.
* **Instruções Condicionais no Prompt:** As instruções para incluir características de itens e preços são adicionadas ao prompt somente quando necessário, tornando a interação mais natural.
* **Cores no Texto:**  A cor verde na resposta do NPC ajuda a distinguir o diálogo do NPC das entradas do jogador.
* **Loop de Interação com "SAIR":** O uso de "SAIR" para encerrar a conversa torna a interação mais intuitiva para o jogador.
