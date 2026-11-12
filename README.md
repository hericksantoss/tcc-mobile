# Towers Admin — app de gestão de condomínio

App Android desenvolvido como **Trabalho de Conclusão de Curso** no Senai (2021). Ele conecta moradores e
síndico para a comunicação e a rotina do condomínio.

## Funcionalidades

- **Login separado para morador e síndico**, com autenticação por token (JWT) guardado na sessão e enviado
  automaticamente nas requisições por um interceptor do OkHttp
- **Mural de avisos**: o síndico cria, edita e exclui avisos, e o morador acompanha
- **Visitantes**: cadastro e listagem de visitantes, tanto pelo morador quanto pelo síndico
- **Agendamento de espaços** comuns (salão de festas, churrasqueira etc.)
- **Chat em tempo real** entre morador e síndico, via Socket.IO
- Telas de **votações online** e **reclamações** (interface)

## Stack

- **Kotlin**, Android SDK (minSdk 26)
- **Retrofit + Gson** para consumir a API REST
- **OkHttp** com interceptor de autenticação
- **Socket.IO** para o chat
- RecyclerView com adapters próprios para as listagens

## Estrutura

```
app/src/main/java/com/example/towersadmin/
  api/          cliente Retrofit e definição dos endpoints
  adapters/     adapters das listas (avisos, visitas, agendamentos)
  chat/         sala de chat com Socket.IO
  data/         modelos (Condomínio, Bloco, Apartamento, Morador, Síndico...)
  requests/     corpos das requisições   (pasta "resquests" no código)
  responses/    respostas da API
  ui/           telas: login, dashboards, avisos, visitantes, agendamento
  utils/        sessão (token), máscaras de campos, constantes
```

## Como rodar

1. O app consome uma API Node.js desenvolvida pelo grupo
   ([TCC-CONDOMINIO](https://github.com/ThamiresAmancio/TCC-CONDOMINIO)). Suba essa API localmente.
2. Em `utils/Constants.kt`, troque o IP em `localhost` pelo endereço da máquina onde a API está rodando.
3. Abra o projeto no Android Studio e rode em um emulador ou aparelho com Android 8.0+.

## Equipe

Projeto em grupo no Senai. Este repositório é o app mobile; a maior parte dos commits é minha.
