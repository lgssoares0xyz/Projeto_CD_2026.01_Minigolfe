# Projeto_CD_2026.02_Minigolfe
Projeto Final de Circuitos Digitas, 1º Semestre de 2026, com o professor Fábio Cappabianco, ICT Unifesp. Desenvolvido no software de simulação de circuitos digitas WiRedPanda.

- Lucas Gabriel de Souza Soares (185286)
- Misael Denis de Abreu Leite (185307)
- Victor Antônio Canassa (185333)

# Níveis

- Nível 1 (Básico) ✅
Golfe com obstáculos e lançamento em ângulo a partir de uma posição inicial horizontal fixa. Apenas uma fase.
- Nível 2 (Desejado) ✅
Todos os anteriores, mas com posição inicial variável (jogador pode escolher a posição horizontal de lançamento). Apenas uma fase.
- Nível 3 (Ambicioso) ❌
Todos os anteriores, mas com 3 fases e um sistema de vidas para reset do jogo no game over.

# Vídeo demonstrativo
https://www.youtube.com/watch?v=xaYWrRXTZXA
# Sobre a implementação

O campo do jogo é uma matriz de LEDs 8x24, que conta com obstáculos (pedras e bombas) e um buraco. O objetivo do jogo é lançar a bola e atingir o buraco dentro do tempo limite e sem encostar em bombas. A posição da bola fica guardada em registradores de 3 bits (para a coordenada X) e 5 bits (para a coordenada Y), e a renderização da bola na matriz de LEDs é controlada por uma matriz de ANDs e decodificadores de 3 e 5 bits. A bolinha é lançada da parte inferior do mapa, e é possível escolher:
1 - posição horizontal de lançamento
2 - ângulo de lançamento (8 direções da rosa dos ventos)
O ângulo de lançamento define como será o incremento/decremento nas coordenadas da posição da bolinha a cada ciclo do clock. 

# Como jogar

- Inicialmente, a bolinha estará oscilando no eixo X, aguardando que seja selecionada a posição inicial de lançamento. Apertar \[X\] para escolher.
- Agora a bolinha estará parada, esperando que seja escolhido o ângulo (direção) de lançamento. A direção atual pode ser visualizada na rosa dos ventos ao lado. Os ângulos são alternados muito rapidamente, o que foi feito para elevar o nível de dificuldade. Apertar \[X\] para escolher.
- A bolinha tem cerca de 7 segundos para atingir o buraco. Uma vez que o cronômetro chega em 7, o jogo reinicia. Se a bolinha encostar em uma bomba, ela explodirá e o jogo irá reiniciar quando o cronômetro chegar em 7. Ou, é possível simplesmente apertar R (botão de reset), o que fará com que o jogo reinicie imediatamente. 

# Dificuldades e melhorias

- Tivemos dificuldades em preparar o projeto para o nível 3 desde o início. Deveríamos ter usado multiplexadores na matriz de ANDs, a fim de fazer a transição entre níveis, mas não tivemos essa visão logo de cara.
- A bolinha pisca quando colide com pedras, o que também não soubemos contornar uma vez que o circuito sequencial ficou grande e complexo.
- Tivemos dificuldade em lidar com múltiplas fontes de dados para o mesmo registrador, o que é essencial para a mecânica do jogo.
- Tivemos dificuldade em integrar a máquina de estados que controla o fluxo do jogo com todos os outros elementos combinacionais do circuito.
