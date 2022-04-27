# Neural-Networks-and-Deep-Learning

João Arthur Gaia

Jonh Lucas Alves

## Background Search

### Trabalho a ser reproduzido

O [trabalho](https://paperswithcode.com/paper/bag-of-tricks-for-efficient-text) a ser reproduzido 
foi desenvolvido por pesquisadores do facebook, e tem como objetivo apresentar um classificador de texto
de alta capacidade e velocidade, com a mesma precisão de outros do tipo.

O trabalho possui 57 implementações no paperswithcode, a implementação original é feita em C/C++,
E um módulo Python foi feito para difundir seu uso.
Mas há implementações utilizando PyTorch, Tensorflow, Mxnet e até MindSpore.

Sua performance competitiva e sua velocidade muito acima da média podem ser vistas
em diferentes datasets na figura a seguir:

![bag of tricks](https://github.com/jagra26/Neural-Networks-and-Deep-Learning/blob/main/bag%20of%20tricks.jpg)

### General Search

A principal referência sobre o trabalho é a [pagina](https://fasttext.cc) da biblioteca referente a ele.
O [vídeo](https://youtu.be/og183Y9yHFs) explica em poucas palavras o propósito desse classificador.
Há documentação referente a instalação e utilização do módulo em python.

Segundo a divisão de [IA do Facebook](https://ai.facebook.com/tools/fasttext/) (tradução livre):

FastText é uma biblioteca leve projetada para ajudar a criar soluções escaláveis para representação 
e classificação de texto. Funciona em hardware padrão e genérico e pode até caber em smartphones e 
computadores pequenos por meio de funcionalidade que reduz a memória consumida pelos modelos fastText.

Também ressalta que há modelos pré treinados para 157 línguas diferentes, treinados com dados da wikipédia.

### Specific Search

O artigo 
[Which Encoding is the Best for Text Classification in Chinese, English, Japanese and Korean?](https://paperswithcode.com/paper/which-encoding-is-the-best-for-text)
discorre sobre diferentes classificadores, em diferentes idiomas e classificações.
Chegando a conclusão que o fastText é de fato muito mais rápido e leve que os demais, não precisando de GPU.
Como pode ser visto na figura a seguir:

![CJK](https://github.com/jagra26/Neural-Networks-and-Deep-Learning/blob/main/CJK.jpg)

O fastText tem o melhor resultado para as linguas CJK com codificação character-level n-gram.
Já em inglês, o fastText performou melhor com a codificação word-level n-grams. 
Nessa mesma codificação, o fastText tem performance equivalente a outros classificadores para CJK.
Ainda conclui que o fastText tem uma tendência maior ao overfitting que redes convolucionais.

Já o artigo [FastText.zip: Compressing text classification models](https://paperswithcode.com/paper/fasttextzip-compressing-text-classification),
parte do fastText original para desenvolver um algoritmo de compactação. Perde um pouco da precisão, porém tem melhorias consideraveis no uso de 
memória e CPU. Sendo publicado como uma extensão do fastText original.

Uma comparação entre diferentes algoritmos de compressão em diferentes tamanhos de modelo pode ser vista na figura a seguir:

![zip](https://github.com/jagra26/Neural-Networks-and-Deep-Learning/blob/main/zip.jpg)

O artigo [https://paperswithcode.com/paper/fast-linear-model-for-knowledge-graph](https://paperswithcode.com/paper/fast-linear-model-for-knowledge-graph),
utiliza o fastText como plataforma para desenvolver uma baseline baseada em representação Bag of Words (BoW). Que aprende com "graphs embeddings". 
Criando bases de conhecimento e resolvendo problemas de aprendizado supervisionado.

Uma comparação entre a acurácia de diferentes metodos pode ser vista a seguir:

![graph](https://github.com/jagra26/Neural-Networks-and-Deep-Learning/blob/main/graph.jpg)

No Arigo [How Effective is Incongruity? Implications for Code-mix Sarcasm Detection](https://paperswithcode.com/paper/how-effective-is-incongruity-implications-for),
utiliza-se o fastText para se desenvolver um modelo de detecção de sarcasmo associado ao uso de "code-mix language". Chegando a um resultado tão efetivo quanto
modelos pré-treinados, com um tempo de treinamento 10 vezes mais curto e com uso de memória reduzido.

A aruitetura do projeto, contendo o fastText, pode ser vista a seguir:

![sarcasm](https://github.com/jagra26/Neural-Networks-and-Deep-Learning/blob/main/sarcasm.jpg)

No paper [Imputing Out-of-Vocabulary Embeddings with LOVE Makes Language Models Robust with Little Cost](https://paperswithcode.com/paper/imputing-out-of-vocabulary-embeddings-with), 
propõe-se um framework de aprendizado robusto a palavras fora do vocabulário (OOV), o calcanhar de Aquiles da maioria das soluções de NLP. Para tal utiliza modelos pré
treinados como BERT. E melhora a robustez desses modelos, como o próprio fastText, como pode ser visto a seguir:

![LOVE](https://github.com/jagra26/Neural-Networks-and-Deep-Learning/blob/main/LOVE.jpg)

[Attention Is All You Need](https://doi.org/10.48550/arXiv.1706.03762)

O artigo ocupa-se na tarefa de tradução automática. Propondo uma arquitetura que dispensa a necessidade de recorrências e convoluções. O apelo modelo está na adoção de attention mechanism, que resultou em traduções de maior qualidade, mais paralelismo e um menor tempo de treinamento.
Tanto para tradução Inglês-Alemão e Inglês-Francês, o modelo apresentou ótimos resultados. Desde os modelos mais básicos até os maiores (big Transformer) mostraram-se competitivos, mesmo com tempo de treinamento de apenas 3 dias. As comparações foram realizadas com base na pontuação BLEU.
Um passo futuro é a adoção de entradas e saídas não textuais para modelos baseados em attention, ou seja, investigar métodos eficientes para lidar com imagem, áudio e vídeo.

[Character-based Neural Networks for Sentence Pair Modeling](https://arxiv.org/abs/1805.08297) aborda o pareamento de sentenças realizando as tarefas de paraphrase identification, semantic textual similarity, and natural language inference. Diferentemente da maioria dos modelos, o experimento propôs a utilização de uma granularidade fina, utilizando-se de sub-palavras, invés de incorporar um conjunto de palavras pré treinadas.
Foram comparados resultados de diferentes redes com hiperparâmetros de modelo que estão de acordo com estado da arte e diferentes granularidades. Por fim, foi adotada uma CNN de 19 layers baseada em PWI. 
Os modelos com palavras incorporadas estão limitados ao conjunto de palavras adicionadas, tais conjuntos não possuem grande desempenho no ambiente de redes sociais. Portanto, o desempenho do modelo de sub-palavras obtido em datasets do Twitter, onde palavras fora do vocabulário cotidiano e com grandes diferenças ortográficas, mostra seu valor.
![sub word](https://github.com/jagra26/Neural-Networks-and-Deep-Learning/blob/main/subwords.png)


