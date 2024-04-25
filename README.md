<h2>Quem faz ganha, quem não faz não perde (atividade opcional)</h2>

Esta atividade vale 3 pontos na ~~Prova 2~~ Prova 1. Para quem depositar o relatório aqui até ~~2a feira~~ 5a feira, ~~a prova vale 7 pontos. Se não, vale 10 pontos~~.

**Atividade**: 

***Nota adicionada 23/04 - 13:11**
Para a atividade opcional "Quem faz ganha, quem não faz não perde", o data tem 14400 pontos. Isso corresponde a 5 dias x 24 h x 60 min x 2 = 14400, que vem de uma leitura a cada 30s. Como o tempo de processamento ficou mais alto do que eu esperava, pode fazer com dados de 2 dias, ou seja, 2x24x60x2 = 5760 pontos.

(a) Obtenha a Matriz de Entropias de Cópulas entre os pares de séries temporais (ST) do data set subsfin fornecido. Talvez fique melhor trabalhar com as STs de diferenças e não com as originais. O data set tem 52 STs, portanto a matriz será 52x52.
Roteiro: Siga esta 'receita' para obter cada distribuição cópula e encontre um pacote python (tem vários!) que calcula a entropia de cópula, para colocar na matriz.   https://twiecki.io/blog/2018/05/03/copulas/

(b) Em seguida, utilizando a matriz de entropia de cópulas, escolha, para cada ST aquelas com maior e com menor entropia de cópula, e mostre as duas imagens das cópulas uma ao lado da outra para comparação.

Relatório: Um único PDF com os códigos e os resultados. Não quero executar os seus códigos, vou apenas inspecionar no PDF se eles realmente geram os resultados apresentados. Sei que o relatório vai ficar grande, mas não vai ser impresso e não tem peso. Também não precisa muita formatação - basta copiar e colar com um pouco de organização, pois queremos discutir os resultados.

Na "receita" você também vai aprender muito sobre cópulas. Pode me remeter qualquer questão que precisar, enquanto estiver fazendo. É importante que quem for fazer faça individual para vermos se os resultados conferem e entender o porque, se não conferirem.

Pode ser util para alguém: O código python simples abaixo carrega as STs para X e calcula as STs de diferenças em Xd. E "Mostra, se quiser ver!".

```python
import numpy as np
import matplotlib.pyplot as plt

X = np.genfromtxt('subsfin.txt')
print(X.shape)

## Mostra, se quiser ver
##for i in range(X.shape[1]):
##    plt.plot(X[:,i])
##    plt.show()
##    input()
################  Séries de diferenças
Xd = np.zeros(X.shape)
for i in range(X.shape[0]-2):
    Xd[i+1,:] = X[i+1,:] - X[i,:]
print(Xd.shape)

## Mostra, se quiser ver
##for i in range(Xd.shape[1]):
##    plt.plot(Xd[:,i])
##    plt.show()
##    input()
```
