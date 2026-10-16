# QuadParty Online — hospedagem pelo jogador (WebRTC P2P)

O criador da sala é o host e executa a simulação dos quatro minijogos no próprio navegador. Os demais jogadores se conectam ao host por WebRTC DataChannels. Não há servidor Node.js de partidas.

## Iniciar

Publique a pasta `public/` em hospedagem estática HTTPS (GitHub Pages, Netlify, Vercel) ou teste localmente com `python3 -m http.server 8000` dentro de `public/`, abrindo http://localhost:8000. O arquivo `index.html` não deve ser aberto via `file://`.

Clique **Criar sala**. Compartilhe o código ou link. Até três amigos entram e o host seleciona e inicia os jogos.

## Dependências e limitações

O cliente PeerJS é carregado por CDN e usa o servidor público de sinalização PeerJS para descobrir peers. O tráfego de jogo ocorre por WebRTC entre dispositivos quando possível. Redes com NAT restritivo podem impedir conexão sem servidor TURN; o projeto não configura TURN próprio. É necessário internet para sinalização. Não há reconexão/migração automática de host; ao fechar o navegador do host, a partida termina. O host tem autoridade sobre o estado e pode adulterá-lo; não é anti-cheat. A disponibilidade do serviço público de sinalização não é garantida.

Minijogos: Snake Arena, Batalha de Arena, Corrida Turbo, Jogo da Velha.
