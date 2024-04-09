Deseja-se construir o controlador de um robô capaz de remover detritos não metálicos de uma tubulação metálica. A figura ilustra o problema:
![image](https://github.com/FelipMa/diagrama-de-estados-robo-limpa-tubos/assets/105306441/440e07f3-3909-49f7-8e79-827ed867579d)

A tubulação a ser percorrida corresponde aos componentes de uma matriz de células, indicados pela cor cinza. O robô, mostrado como uma seta, é colocado em uma célula da cor preta, a qual representa um ponto de acesso do sistema de tubulação, com sua frente voltada para qualquer um dos 4 sentidos possíveis (Norte, Sul, Leste ou Oeste). O robô possui 4 sensores binários:

- head (H): detector de metal de curto alcance, situado na frente do robô (ponta da seta), que retorna 0 quando a célula situada à frente do robô está livre para prosseguir (célula cinza ou preta) – caso contrário, retorna 1;
- left (L): detector de metal de curto alcance, situado na lateral esquerda do robô, que retorna 0 quando a célula do lado esquerdo do robô está livre (ou seja, há uma abertura à esquerda na tubulação) – caso contrário, retorna 1;
- under (U): sensor situado na parte inferior do robô, que retorna 1 quando a célula na qual o robô está situado é preta – caso contrário, retorna 0; e
- barrier (B): sensor situado na frente do robô, que retorna 1 quando a célula situada à frente do robô está bloqueada por algum entulho que o robô é capaz de remover (células com losango) – caso contrário, retorna 0.

Em relação à movimentação, o robô é capaz de fazer apenas 2 tipos de movimento: avançar para uma célula livre à sua frente (saída F) ou rotacionar 90o para a esquerda, mantendo-se na mesma célula em que se encontra (saída T). Cada movimento consome 1 pulso de clock. Ao passar de uma célula livre para uma célula preta ou, ainda, em casos anômalos, o robô deverá ficar suspenso (em stand-by), até que um novo reset seja dado. Ao deparar-se com algum entulho à sua frente, o robô consumirá ao menos 3 pulsos de clock para removê-lo (saída R), após o que poderão ocorrer duas situações: i) caso reste algum entulho, o robô fará novo ciclo de remoção (3 pulsos) e testará a condição de caminho livre novamente; ii) caso o caminho esteja livre (não há mais entulho na célula considerada), o robô entrará em movimento novamente, avançando sobre o setor antes ocupado pelo entulho. O robô deverá ser capaz de percorrer toda a tubulação de forma otimizada, adotando sempre o mesmo critério em todas as bifurcações, qual seja, adotar o lado esquerdo como preferencial.

1. Faça o diagrama de estados da FSM que atenda ao solicitado, utilizando uma máquina de
Mealy. Associe um número a cada estado, iniciando com 0 (zero) para o estado inicial.
2. Seguindo o diagrama de estados construído na questão anterior, dê um Reset e realizem 22 pulsos de clock, completando a tabela seguinte.

![image](https://github.com/FelipMa/diagrama-de-estados-robo-limpa-tubos/assets/105306441/1b40518e-dab1-42f5-b700-78fb7b718469)
