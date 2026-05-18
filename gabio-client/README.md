# gabio-client — Gabio Bank

**Parte entregue pelo grupo (frontend):** cliente web em HTML + TypeScript que consome o protocolo **GBTP** via WebSocket.

## Requisitos

- Node.js 18+
- Servidor GBTP do backend do grupo em `ws://localhost:3000`  
  (para testar sozinho, use o `../server` — não vai na entrega)

## Instalação e execução

```bash
npm install
npm start
```

| Comando        | Descrição                    |
|----------------|------------------------------|
| `npm start`    | Sobe o cliente (Parcel)      |
| `npm run dev`  | Igual ao start, abre o browser |
| `npm run build`| Build em `dist/`             |

## Uso

1. Peça para o backend subir o **gabio-server** na porta 3000 (ou use `../server` só para teste local).
2. Acesse o cliente e informe o ID da conta (ex.: `1001`).
3. Use **Depositar**, **Sacar**, **Transferir** ou **Atualizar saldo**.

## Estrutura

```
gabio-client/
├── index.html
├── style.css
├── package.json
├── tsconfig.json
└── src/
    ├── main.ts
    ├── core/
    │   ├── BankService.ts
    │   └── GbtpProtocol.ts
    ├── views/
    │   ├── LoginView.ts
    │   └── DashboardView.ts
    ├── controllers/
    │   └── AccountController.ts
    ├── models/
    │   └── Account.ts
    └── utils/
        └── toast.ts
```

## Protocolo GBTP (requisição)

| Campo           | Descrição                                              |
|-----------------|--------------------------------------------------------|
| `OPERATION`     | `BALANCE`, `DEPOSIT`, `WITHDRAW`, `TRANSFER`           |
| `ACCOUNT_ID`    | Conta principal                                        |
| `TO_ACCOUNT_ID` | Destino (só `TRANSFER`; vazio nos demais)              |
| `VALUE`         | Valor (`0.00` em `BALANCE`)                            |

Exemplo:

```
OPERATION:DEPOSIT
ACCOUNT_ID:1001
TO_ACCOUNT_ID:
VALUE:100.00
```

## Protocolo GBTP (resposta)

| Campo     | Descrição        |
|-----------|------------------|
| `STATUS`  | `OK` ou `ERROR`  |
| `MESSAGE` | Texto descritivo |
| `BALANCE` | Saldo da conta   |

O cliente exibe o saldo na tela e notificações com `MESSAGE` e `STATUS`.
