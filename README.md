🚚 Problema do Caixeiro Viajante (TSP) com Heurísticas de Inserção
```
modelagem e construção de rotas aproximadas para o Problema do Caixeiro Viajante, através da implementação de heurísticas de inserção utilizando estruturas de dados e algoritmos clássicos em Java.

Apresentação
🔗 

##📌 Sobre o Projeto

O programa resolve o Problema do Caixeiro Viajante (TSP), onde um conjunto de cidades deve ser percorrido com a menor distância possível.

Como a solução ótima é computacionalmente custosa, o projeto utiliza heurísticas de inserção para construir soluções aproximadas.

🔹 Vértices: representam cidades no plano cartesiano (x, y)
🔹 Arestas: representam a distância entre cidades
🔹 Tour: ciclo que visita todas as cidades

🎯 Objetivos
Construir rotas aproximadas para o TSP
Implementar heurísticas de inserção
Comparar estratégias de construção de soluções
Visualizar o comportamento do algoritmo
Trabalhar com listas encadeadas circulares

🧩 Estrutura do Projeto

t4-tsp/
├── dados/                       # Arquivos de entrada
│   ├── tsp10.txt               # Base para testes
│   └── usa13509.txt            # Entrada oficial (13k cidades)
└── src/                        # Código-fonte
    ├── Main.java               # Execução do programa
    ├── Tour.java               # Estrutura do tour (IMPLEMENTAR)
    ├── Point.java              # Representação das cidades
    ├── TSPVisualizer.java      # Visualização gráfica
    ├── In.java                 # Leitura de arquivos
    ├── StdDraw.java            # Renderização gráfica
    ├── StdIn.java
    └── StdOut.java
```

🧭 Modelagem do Problema

O problema é modelado como um grafo completo ponderado:

Vértices → cidades
Arestas → conexões entre todas as cidades
Peso → distância euclidiana

O tour é representado como uma lista circular encadeada, onde:

Cada nó contém uma cidade
Cada nó aponta para o próximo
O último nó retorna ao primeiro
🔍 Heurísticas Implementadas
📌 Nearest Insertion (Vizinho Mais Próximo)

💡 Ideia:
Inserir a nova cidade próxima da cidade já existente mais próxima no tour.

Passos:
1. Percorrer o tour atual
2. Encontrar o ponto mais próximo de p
3. Inserir p após esse ponto

📎 Exemplo:

Antes: A → B → C → A
Depois: A → p → B → C → A
📌 Smallest Insertion (Menor Aumento)

💡 Ideia:
Inserir a cidade na posição que cause o menor aumento no custo total do tour.

Passos:
1. Para cada aresta (A → B)
2. Calcular custo = dist(A,p) + dist(p,B) - dist(A,B)
3. Escolher o menor custo
4. Inserir p entre A e B

📎 Exemplo:

Antes: A → B → C → A
Depois: A → B → p → C → A
📥 Formato da Entrada
largura altura
x0 y0
x1 y1
x2 y2
...
Primeira linha: dimensão do plano
Linhas seguintes: coordenadas das cidades

##▶️ Como Executar

Clone o repositório:
git clone <seu-repositorio>

Acesse a pasta:
cd t4-tsp/src

```
Execute:
java Main ../dados/usa13509.txt
🧪 Testes e Validação
```

```
Utilize os arquivos:

tsp10.txt              → entrada base
tsp10-nearest.txt      → resultado esperado (Nearest)
tsp10-smallest.txt     → resultado esperado (Smallest)
tsp10-optimal.txt      → solução ótima
```

📊 Conclusão
```
O projeto demonstra como heurísticas simples podem resolver problemas complexos de forma eficiente.

Nearest Insertion: simples e rápida
Smallest Insertion: geralmente produz melhores resultados

Ambas permitem trabalhar com grandes volumes de dados, como o arquivo usa13509.txt.
```
