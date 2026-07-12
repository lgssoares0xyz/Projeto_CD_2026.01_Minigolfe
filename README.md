# Projeto_CD_2026.02_Minigolfe
Projeto Final de Circuitos Digitas, 2º Semestre de 2026, com o professor Fábio Cappabianco, ICT Unifesp. Desenvolvido no software de simulação de circuitos digitas WiRedPanda.

- Lucas Gabriel de Souza Soares (185286)
- Misael Denis de Abreu Leite (185307)
- Victor Antônio Canassa (185333)

# Níveis

- Nível 1 (Básico)
Golfe com obstáculos e lançamento em ângulo a partir de uma posição inicial horizontal fixa. Apenas uma fase.
- Nível 2 (Desejado)
Todos os anteriores, mas com posição inicial variável (jogador pode escolher a posição horizontal de lançamento). Apenas uma fase.
- Nível 3 (Ambicioso)
Todos os anteriores, mas com 3 fases e um sistema de vidas para reset do jogo no game over.

# Vídeo demonstrativo

(Link pro vídeo no YouTube)

# Sobre a implementação

O campo do jogo é uma matriz de LEDs 8x24, que conta com obstáculos (pedras e bombas) e um buraco. O objetivo do jogo é lançar a bola e atingir o buraco dentro do tempo limite e sem encostar em bombas. A posição da bola fica guardada em registradores de 3 bits (para a coordenada X) e 5 bits (para a coordenada Y), e a renderização da bola na matriz de LEDs é controlada por uma matriz de ANDs e decodificadores de 3 e 5 bits. A bolinha é lançada da parte inferior do mapa, e é possível escolher:
1 - posição horizontal de lançamento
2 - ângulo de lançamento (8 direções da rosa dos ventos)
O ângulo de lançamento define como será o incremento/decremento nas coordenadas da posição da bolinha a cada ciclo do clock. 

...

# Dificuldades e melhorias
