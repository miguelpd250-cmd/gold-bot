 # GOLD BOT — WhatsApp

Bot de economia virtual/RPG para grupos de WhatsApp, feito em Node.js + Baileys + SQLite.

## Requisitos
- Node.js 20 ou superior
- WhatsApp no celular para escanear o QR Code
- VS Code (opcional)

## Instalação
1. Extraia o ZIP e abra a pasta `gold-bot` no VS Code.
2. Abra o terminal dentro da pasta.
3. Execute `npm install`.
4. Copie `.env.example` para `.env` (opcional: ajuste valores).
5. Execute `npm start`.
6. Escaneie o QR Code em WhatsApp > Aparelhos conectados > Conectar aparelho.
7. Adicione o número conectado ao grupo.

## Comandos
Digite `!menu` no grupo para ver a lista completa.

### Economia
- `!gold`, `!daily`, `!pescar`, `!minerar`, `!rank`
- `!loja`, `!comprar ferro`, `!minhapicareta`, `!reparar`
- `!roubargold @pessoa`

### Apostas Gold (moedas virtuais)
- `!apostar` mostra regras
- `!roleta 500 vermelho` (também preto/verde)
- `!dados 500`
- `!caraoucoroa 500 cara` (ou coroa)
- `!blackjack 500`
- `!historicoapostas`

O limite máximo é 10.000 GOLD por aposta e o mínimo é 10 GOLD. Não há dinheiro real, depósitos ou saques.

### Banco
- `!banco`
- `!investir 10000 7` (planos de 1, 3, 7, 15 ou 30 dias)
- `!meusinvestimentos`
- `!resgatar ID`

O principal fica bloqueado até o vencimento. O resgate é manual pelo comando.

### RPG / Arena
- `!rpg` ou `!perfil`
- `!arena`, `!boss`, `!batalhar`
- Chefes liberados conforme o nível do jogador. Cada jogador tem sua própria barra de vida do chefe.

### Ofensiva
Uma mensagem normal no grupo conta como atividade diária. Comandos iniciados por `!` não contam. A sequência é por dia no fuso configurado em `.env` e pode ser perdida se o jogador passar um dia sem falar. Marcos de 3, 7, 15, 30 e 60 dias dão bônus uma vez por sequência atingida.

## Dados e segurança
- O banco `goldbot.sqlite` é criado automaticamente na primeira execução.
- A sessão fica em `auth_info/`. Não compartilhe essa pasta nem o arquivo `.env`.
- Faça backup do arquivo SQLite antes de atualizar o projeto.
- Baileys é uma biblioteca não oficial para WhatsApp Web. O uso pode contrariar os termos do WhatsApp e existe risco de desconexão ou restrição do número. Para uso comercial/produção, avalie as APIs oficiais da Meta e suas limitações.
- Use apenas em grupos onde os participantes saibam que o bot está ativo. Evite spam e mensagens automáticas excessivas.

## Observações
Este projeto é um ponto de partida funcional. Teste em um grupo privado antes de usar em um grupo ativo. O sistema de ofensiva registra uma vez por dia quando o jogador envia mensagem normal; o aviso de recompensa é enviado quando o usuário executa um comando após atingir um marco, ou na próxima interação comandada.
