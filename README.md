VTT Master 2.0
Descrição
O VTT Master 2.0 é uma aplicação web de Virtual Tabletop (VTT) voltada para sessões de RPG, permitindo a criação e gerenciamento de mapas, tokens e interação em tempo real entre múltiplos usuários por meio de conexão peer-to-peer.
O sistema foi desenvolvido com foco em desempenho, flexibilidade e controle avançado de cena, incluindo suporte a camadas visuais (layers), desenho em tempo real e navegação dinâmica com rotação de câmera.

Tecnologias Utilizadas
JavaScript (Vanilla)
HTML5 Canvas
WebGL (via Three.js)
PeerJS
WebRTC

Funcionalidades
Sistema Multiplayer
Criação de sessões no modo host (mestre)
Conexão de jogadores por meio de ID de sala
Sincronização em tempo real de estado (tokens, desenhos e mapa)
Controle de permissões por usuário

Sistema de Tokens
Criação de tokens personalizados
Suporte a diferentes formatos:
Círculo
Quadrado
Imagem (PNG)
Propriedades configuráveis:
Posição
Rotação
Escala
Inversão horizontal (flip)
Cor
Controle de propriedade (ownership) por usuário

Sistema de Camadas (Layers)
Tokens podem possuir múltiplas camadas visuais
Cada camada suporta:
Imagem própria
Deslocamento (offset X/Y)
Rotação
Escala
Opacidade
Ordem de renderização (Z-index)
Possibilita:
Representação de equipamentos
Estados visuais (ex: caído)
Efeitos gráficos adicionais

Sistema de Mapa
Upload de imagens como mapa base
Controle de posição e escala do mapa
Sincronização automática entre participantes

Sistema de Desenho
Ferramenta de desenho livre em tempo real
Configuração de cor e espessura do traço
Sincronização entre todos os usuários conectados

Sistema de Medição
Ferramenta de régua para cálculo de distâncias
Integração com sistema de grade
Feedback visual dinâmico

Navegação
Movimentação do viewport (pan)
Zoom dinâmico via scroll
Controle por teclado (WASD)
Suporte à rotação da câmera em ambiente 2D

Sistema de Estado
Estrutura centralizada para gerenciamento da aplicação
Controle dos seguintes elementos:
Tokens
Desenhos
Mapa
Parâmetros de visualização (câmera)
Exportação e importação de estado em formato JSON

Arquitetura
Estrutura Geral
state: responsável pelo estado global da aplicação
net: gerencia a comunicação em tempo real via WebRTC
draw(): motor de renderização 2D baseado em canvas
Three.js: camada adicional para renderização 3D
Interface: gerenciamento de eventos e interação do usuário

Fluxo de Sincronização
O host inicia a sessão e gera um ID
Os clientes se conectam utilizando esse ID
O host envia o estado completo inicial
Os clientes sincronizam localmente
Alterações são propagadas em tempo real para todos os participantes

Modelo de Dados (Simplificado)
{
  "tokens": [],
  "drawings": [],
  "gridSize": 50,
  "pan": { "x": 0, "y": 0, "scale": 1, "rot": 0 },
  "map": { "imgSource": null, "x": 0, "y": 0, "scale": 1 }
}


Execução
Baixar o arquivo HTML do projeto
Abrir o arquivo em um navegador compatível
Selecionar:
"Criar Nova Sala" para iniciar como host
"Entrar na Sala" para conectar como cliente
Compartilhar o ID da sala com outros usuários

Exportação e Importação
Exportação do estado completo em formato JSON
Possibilidade de salvar e restaurar sessões
Compatível com persistência local de campanhas

Diferenciais Técnicos
Renderização híbrida utilizando Canvas e WebGL
Sistema de camadas dinâmicas para composição visual de tokens
Arquitetura orientada a estado
Comunicação peer-to-peer sem dependência de servidor central
Implementação de rotação de câmera em ambiente 2D

Possíveis Evoluções
Implementação de iluminação dinâmica
Sistema de "fog of war"
Persistência em banco de dados remoto
Sistema de combate e iniciativa
Chat integrado entre usuários

Autor
Projeto desenvolvido com foco em aplicações interativas e sistemas complexos voltados para jogos e simulação.

