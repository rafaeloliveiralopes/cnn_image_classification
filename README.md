# cnn_image_classification

## Sobre o projeto

Este repositório apresenta uma rede neural convolucional (CNN) aplicada ao conjunto de dados MNIST, com o objetivo de classificar dígitos manuscritos (de 0 a 9). A base MNIST é amplamente utilizada para experimentos em Visão Computacional e contém imagens em tons de cinza com dimensão de 28×28 pixels. Graças a seu tamanho e padronização, ela se tornou um padrão de referência para avaliar o desempenho de algoritmos de classificação.

## Arquitetura da Rede e Abordagem

A solução faz uso da biblioteca TensorFlow e da API Keras, que oferecem componentes prontos para construir camadas convolucionais, de pooling e densas de maneira simples e modular.
A arquitetura proposta conta com duas camadas convolucionais (Conv2D), seguidas por uma camada de pooling máximo (MaxPooling2D) para redução dimensional. Posteriormente, são aplicadas camadas de regularização (Dropout) para mitigar problemas de overfitting.
Os recursos extraídos pelas camadas convolucionais são achatados (Flatten) e alimentados a camadas densas (Dense) responsáveis pela classificação final. A ativação softmax na saída permite estimar a probabilidade de cada uma das classes (0 a 9).

## Treinamento e Resultados

Para o treinamento, foi utilizado o otimizador Adam, um otimizador bastante usado pela sua eficiência em problemas de classificação multiclasse, além da função de perda categorical_crossentropy.
Durante o processo de ajuste, a taxa de aprendizado foi controlada pelo callback ReduceLROnPlateau, o qual reduz automaticamente a taxa quando não há melhoria significativa na acurácia de validação por algumas épocas consecutivas.
Como resultado, a rede obteve 99,3% de acurácia no conjunto de treinamento e 99,1% de acurácia no conjunto de validação, evidenciando tanto a eficácia do modelo quanto a adequação das técnicas de regularização empregadas.

## Destaques e Aprendizados

A CNN demonstrou excelente capacidade de extrair features relevantes automaticamente, diferentemente de métodos tradicionais que requerem a engenharia manual de atributos.
Foi aprofundado o entendimento sobre processos de detecção e segmentação, que expandem o escopo das aplicações de Visão Computacional para além da simples classificação.
A experiência reforçou a importância de bons métodos de regularização e estratégias adequadas de otimização, que mantiveram baixas as taxas de overfitting, resultando em generalização robusta.

## Conclusão

Embora o MNIST seja um conjunto de dados relativamente simples, a arquitetura e as técnicas empregadas podem ser facilmente adaptadas a cenários mais complexos, como classificação de imagens em cores ou análise de imagens médicas, colaborando com a descoberta precoce de doenças imperceptíveis ao olho humano.
A base construída aqui pode servir como ponto de partida para o treinamento de redes mais profundas (e.g., Inception, ResNet) ou integrações com outras áreas de Inteligência Artificial.

Em resumo, este projeto ilustra o pipeline completo de uma CNN para classificação de dígitos, cobrindo desde o pré-processamento dos dados até a avaliação do modelo treinado. O elevado desempenho alcançado no MNIST confirma a confiabilidade dessa abordagem em problemas de classificação de imagens e abre caminho para aplicações mais avançadas em diversas áreas.
