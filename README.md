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

Chega a conclusão que o fastText é de fato muito mais rápido e leve que os demais, não precisando de GPU.

O fastText tem o melhor resultado para as linguas CJK com codificação character-level n-gram.

Em inglês, o fastText performou melhor com a codificação word-level n-grams. 
Nessa mesma codificação, o fastText tem performance equivalente a outros classificadores para CJK.

Ainda conclui que o fastText tem uma tendencia maior ao overfitting que redes convulucionais.


Já o artigo [FastText.zip: Compressing text classification models](https://paperswithcode.com/paper/fasttextzip-compressing-text-classification),
parte do fastText original para desenvolver um algoritmo de compactação. Perde um pouco da precisão, porém tem melhorias consideraveis no uso de 
memória e CPU. Sendo publicado como uma extensão do fastText original.

O artigo [https://paperswithcode.com/paper/fast-linear-model-for-knowledge-graph](https://paperswithcode.com/paper/fast-linear-model-for-knowledge-graph),
utiliza o fastText como plataforma para desenvolver uma baseline baseada em representação Bag of Words (BoW). Que aprende com "graphs embeddings". 
Criando bases de conhecimento e resolvendo problemas de aprendizado supervisionado.

No Arigo [How Effective is Incongruity? Implications for Code-mix Sarcasm Detection](https://paperswithcode.com/paper/how-effective-is-incongruity-implications-for),
utiliza-se o fastText para se desenvolver um modelo de detecção de sarcasmo associado ao uso de "code-mix language". Chegando a um resultado tão efetivo quanto
modelos pré-treinados, com um tempo de treinamento 10 vezes mais curto e com uso de memória reduzido.

No paper [Imputing Out-of-Vocabulary Embeddings with LOVE Makes Language Models Robust with Little Cost](https://paperswithcode.com/paper/imputing-out-of-vocabulary-embeddings-with), 
propõe-se um framework de aprendizado robusto a palavras fora do vocabulário (OOV), o calcanhar de Aquiles da maioria das soluções de NLP. Para tal utiliza modelos pré
treinados como BERT e tem sua perfomance melhorada com o fastText.
