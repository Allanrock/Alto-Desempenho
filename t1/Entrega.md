####Nome: Allan Cerentini
####Disciplina: ELC893 - PROGRAMAÇÃO DE ALTO DESEMPENHO

####Programa escolhido: NQueens - https://pm.bsc.es/projects/bots
####Descrição: 
NQueens é um problema que consiste em colocar N rainhas em um tabuleiro de xadres de tamanho N por N, onde que nenhuma rainha possa atacar a outra. O problema é solucionado quando nenhuma rainha compartilha sua linha, diagonal e coluna com qualquer uma das existentes no tabuleiro. Neste trabalho N possui valor 13.

#### Desempenho:
| # Threads | 1       | 2           |
|-----------|---------|-------------|
| 1         | 8.04619 | 4.86797     |
| 2         | 8.03860 | 4.43258     |
| 3         | 8.07382 | 4.12457     |
| 4         | 7.93308 | 4.43977     |
| 5         | 7.93568 | 4.12476     |
| Média     | 8.00547 | 4.39793     |
| SpeedUp   | 1       | 1.820282845 |

Compiler Flags = -c -I../..//common -O3   -DIF_CUTOFF-I.

####Análise:
O programa tenta cada posição possível para cada rainha. Para cada posição que o programa tenta alocar a rainha, é verificado se há conflito com outras rainhas já existentes. Caso haja conflito o programa tenta alocar a rainha em uma nova posição e realizando novamente a verificação, caso contrário a rainha acha sua posição. O programa cria uma tarefa para cada tentativa, foi utiliza a técnica "cutting off" para reduzir o over-head associado a criação de tarefas.



####Referências:
https://hbfs.wordpress.com/2012/03/27/openmp-and-the-n-queens-problem/
https://github.com/victoraldecoa/N-Queens-Solver_OpenMP_Example/blob/master/src/nqueens-openmp.c
http://sedici.unlp.edu.ar/bitstream/handle/10915/22888/Documento_completo.pdf?sequence=1
http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.469.8883&rep=rep1&type=pdf
https://books.google.com.br/books?id=DuhrCQAAQBAJ
http://www.drdobbs.com/go-parallel/article/print?articleId=221600649

