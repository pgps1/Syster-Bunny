# Syster Bunny — versão 0.17 (arquitetura modular)

Esta versão separa funcionalidades em módulos sem alterar intencionalmente a identidade visual ou as mecânicas existentes.


## Organização

- `index.html`: estrutura da página.
- `styles.css`: estilos e animações visuais.
- `src/app.js`: inicialização e coordenação geral do jogo.
- `src/core/`: utilitários compartilhados.
- `src/data/`: catálogo de itens e falas.
- `src/features/`: funcionalidades completas, como supermercado e minijogo.
- `src/services/`: serviços externos ao fluxo do jogo, como salvamento.
- `src/systems/`: regras de humor e cálculos do céu.
- `Syster-Bunny-v0_13-original.html`: cópia de referência da versão original.

## Módulos separados nesta etapa

- `features/supermarket.js`: compras, inventário, geladeira, despensa, alimentação e arrastar/soltar.
- `features/garden-game.js`: minijogo de caça às borboletas.
- `systems/mood.js`: cálculo do humor da personagem.
- `systems/sky.js`: cálculos de cores e progressão visual do céu.
- `services/storage.js`: leitura e gravação do progresso local.
- `core/utils.js`: funções utilitárias.
- `data/dialogues.js`: falas da personagem.



## Correções da versão 0.16

- Passeios autônomos entre quarto, banheiro, jardim, sala e cozinha.
- Indicador de fome da 0.16 (0% = sem fome) — substituído na 0.17, veja abaixo.
- Recusa de alimentos quando a saciedade já está em 100%, sem consumir o item do inventário.
- Ventilador com acionamento por toque/clique e hélices animadas apenas quando ligado.
- O ventilador só alivia o calor quando está ligado.

## Correções da versão 0.17

- Barra de fome corrigida: agora é **Saciedade** (100% = bem alimentada, 0% = faminta), igual às demais barras.
- Recusa de comida corrigida: ela recusa quando a saciedade chega a 95% (antes só recusava em 100% exato, o que quase nunca acontecia, e o alimento era gasto à toa). Limiar em `FULL_THRESHOLD` (`src/core/utils.js`).
- Ventilador ligado em dia quente agora funciona: antes ela ia ao banheiro por causa do calor e o ventilador nunca a refrescava. Agora ela vai/fica no quarto.
- Fome, limpeza e energia agora são salvas (antes voltavam ao padrão ao recarregar).
- Minijogo: recompensa limitada a 15 moedas (era possível farmar moedas ilimitadas) e limpeza de código morto.
