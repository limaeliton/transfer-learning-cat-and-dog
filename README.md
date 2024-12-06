# Classificador de Cães e Gatos com VGG16

## Introdução

Este projeto implementa um classificador de imagens para distinguir entre cães e gatos, utilizando a arquitetura de rede neural VGG16 e a técnica de *transfer learning*. O objetivo é construir um modelo capaz de classificar imagens de cães e gatos com alta precisão.

## Descrição do Problema

A classificação de imagens é uma tarefa fundamental em Visão Computacional, com aplicações em diversas áreas, como reconhecimento facial, detecção de objetos e diagnóstico médico. Neste projeto, abordamos o problema específico de classificar imagens em duas categorias: cães e gatos.

## Abordagem e Metodologia

A VGG16 é uma rede neural convolucional profunda, amplamente utilizada em tarefas de classificação de imagens. Para este projeto, empregamos a técnica de *transfer learning*, que consiste em utilizar um modelo pré-treinado em um grande conjunto de dados (ImageNet) e adaptá-lo para a nossa tarefa específica. 

O processo de desenvolvimento do classificador envolve as seguintes etapas:

1. **Aquisição e Pré-processamento dos Dados:** O conjunto de dados Cats vs Dogs, disponível através do TensorFlow Datasets, é utilizado para treinar e avaliar o modelo. As imagens são pré-processadas, incluindo redimensionamento e normalização, para garantir compatibilidade com a VGG16.
2. **Construção do Modelo:** O modelo VGG16 pré-treinado é carregado, e suas camadas são congeladas para preservar o conhecimento adquirido durante o treinamento no ImageNet. Em seguida, adicionamos uma nova camada de classificação, composta por uma camada GlobalAveragePooling2D e uma camada Dense com ativação sigmoid, para realizar a classificação binária entre cães e gatos.
3. **Treinamento do Modelo:** O modelo é treinado utilizando o otimizador Adam e a função de perda de entropia cruzada binária. O objetivo é minimizar a perda e maximizar a acurácia durante o treinamento.
4. **Avaliação do Modelo:** Após o treinamento, o modelo é avaliado em um conjunto de dados de teste, separado do conjunto de treinamento, para medir sua performance em dados não vistos. A métrica principal utilizada é a acurácia, que representa a porcentagem de imagens classificadas corretamente.

## Dependências

* Python 3.x
* TensorFlow 2.x
* TensorFlow Datasets
* NumPy
* Matplotlib
