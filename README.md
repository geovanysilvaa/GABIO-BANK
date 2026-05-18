# Gabio Bank — Cliente GBTP (Frontend)

Trabalho da disciplina **Redes de Computadores**.  
**Entrega deste repositório:** apenas o **cliente web** (`gabio-client`).

O protocolo **GBTP** (*Gabio Bank Transaction Protocol*) é consumido via WebSocket. O servidor do grupo roda separadamente em `ws://localhost:3000`.

---

## O que entregar

| Pasta           | Entrega? | Descrição                          |
|-----------------|----------|------------------------------------|
| `gabio-client/` | **Sim**  | Cliente web (HTML + TypeScript)    |
| `server/`       | **Não**  | Servidor local só para você testar |

A pasta `server/` pode ser apagada antes de enviar o trabalho. Ela não faz parte da sua parte (frontend).

---

## Executar o cliente

```bash
cd gabio-client
npm install
npm start
```

Documentação completa do cliente e do protocolo: [gabio-client/README.md](gabio-client/README.md)

---

## Testar sem o servidor do grupo

Se ainda não tiver o backend do grupo, use o servidor temporário em `server/`:

```bash
cd server
npm install
npm start
```

Depois, em outro terminal, suba o `gabio-client` como acima.

Contas de teste: **1001**, **1002**, **1003**.

---

## Integrantes

| Grupo | Integrantes | Papel    |
|-------|-------------|----------|
| —     | —           | Frontend |
| —     | —           | Backend  |
