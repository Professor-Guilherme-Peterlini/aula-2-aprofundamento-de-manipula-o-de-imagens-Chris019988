# Questionário Teórico: Processamento de Imagens com Python

## Instruções
* Responda todas as questões de forma clara e concisa
* Justifique suas respostas quando solicitado
* Tempo estimado: 45 minutos

## Questões

### Parte 1: Conceitos Básicos

1. (2,0 pontos) Explique a diferença entre os métodos de redimensionamento de imagem:
   * Nearest Neighbor
resposta: pode gerar uma imagem ruim ou distorcida com muito zoom, mas é o mais rápido dos tres.

   * Bilinear
resposta: não é tão rápido quanto o neighbor e nem tão preciso com o bicubic, mas produz imagens mais suaves do que os outros.

   * Bicubic
resposta: é o mais lento dos três, mas tambem o mais preciso .

   
2. (1,5 pontos) Por que é importante fazer backup das imagens originais antes de aplicar transformações? Cite dois cenários onde isso é crítico.
resposta: é bom caso perca a imagem ou corrompa e caso faça uma alteração errada.


### Parte 2: Escala de Cinza

3. (2,0 pontos) Compare os dois métodos de conversão para escala de cinza vistos em aula:
   * Média simples dos canais RGB
   * Método por luminosidade (Y = 0.299R + 0.587G + 0.114B)
   
   Por que o segundo método é considerado mais preciso para a percepção humana?
resposta: porque usa coordenadas de cores.


4. (1,5 pontos) Em processamento de imagens, por que frequentemente convertemos uma imagem para escala de cinza antes de aplicar outros algoritmos?
resposta: porque fica mais fácil de trabalhar com ela.


### Parte 3: Detecção de Bordas

5. (2,0 pontos) Explique o funcionamento dos seguintes operadores de detecção de bordas:
   * Sobel
resposta: é uma técnica de detectar as bordas baseadas em um filtro convolucional usando dois kernels para calcular as derivadas parciais da imagem nas direções horizontal e vertical. 

   * Prewitt
resposta: Prewitt é quase igual ao Sobel, mas usa uma versão diferente dos kernels para as direções horizontal e vertical.

   * Laplaciano
resposta: O Laplaciano é um operador de segunda derivada e mede a taxa de variação da inclinação.


6. (1,5 pontos) Na função `pipeline_processamento()` implementada, por que aplicamos equalização de histograma antes da detecção de bordas?
resposta: melhora o contraste da imagem e melhora na detecção de bordas tambem.


### Parte 4: Aplicação Prática

7. (2,0 pontos) Considere o seguinte trecho de código:
```python
img_bordas = img_equalizada.filter(ImageFilter.FIND_EDGES)
img_final = img_bordas.point(lambda x: 255 if x > limiar else 0)
```
   * Qual o propósito da segunda linha?
   resposta: define os pixels como brancos ou pretos.

   * Como a escolha do valor de limiar afeta o resultado final?
   resposta: O valor do limiar determina o quão sensível o algoritmo é às bordas, afetando o número de bordas detectadas.

8. (2,5 pontos) Descreva um pipeline completo para:
   * Detectar bordas em uma imagem com ruído
   * Justifique cada etapa do processo
   * Explique como você escolheria os parâmetros

## Critérios de Avaliação
* Precisão técnica (40%)
* Clareza na explicação (30%)
* Capacidade de relacionar conceitos (30%)

## Bônus (1,0 ponto extra)
Proponha uma modificação no pipeline de processamento que poderia melhorar os resultados em imagens com baixo contraste.
---
**Autor**: [Guilherme Tavares]  
**Data**: [24/01/2025]  
**Versão**: 1.1
