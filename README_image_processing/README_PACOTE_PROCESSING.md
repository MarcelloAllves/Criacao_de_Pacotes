# Classe combination
## Bibliotecas Utilizadas

.  numpy (np): 
    - Biblioteca para computação numérica eficiente. 
      Usada aqui para operações de normalização da imagem de diferença, como encontrar mínimos e máximos.
. skimage.color.rgb2gray:
  - Permite converter imagens RGB em escala de cinza. Facilita operações em que as cores não são relevantes para análise.
. skimage.exposure.match_histograms:
  - Ferramenta para transferir histogramas de intensidade entre imagens, ajustando sua aparência. 
    Útil em processamento de imagens e fotografia digital.
. skimage.metrics.structural_similarity:
  - Calcula a similaridade estrutural entre duas imagens, permitindo identificar diferenças em detalhes estruturais. 
    Amplamente usada em tarefas de comparação e validação de imagens.

## Explicação do Código

### Funções

1. `find_difference(image1, image2)`
   - Compara duas imagens (`image1` e `image2`) de mesma forma, calculando sua similaridade estrutural e gerando uma imagem 
     que representa as diferenças.

   #### Processos importantes:
   - Conversão para escala de cinza: 
     Utiliza `rgb2gray` para transformar as imagens coloridas em tons de cinza, facilitando a análise.
   - Cálculo da similaridade estrutural:
     `structural_similarity` retorna o índice de similaridade entre as duas imagens (0 a 1) e uma imagem de diferença que visualiza 
      onde as discrepâncias estão.
   - Normalização da imagem de diferença:
     Ajusta os valores da imagem de diferença para o intervalo `[0, 1]`, útil para visualização ou processamento adicional.

2. `transfer_histogram(image1, image2)`
   - Ajusta os valores de intensidade da imagem `image1` para corresponder ao histograma de intensidade da imagem `image2`.
   - Usado frequentemente para harmonizar a aparência de duas imagens.


## Aplicações Práticas

. `find_difference`:
  - Controle de qualidade visual, como detecção de mudanças ou erros entre duas versões de uma mesma imagem.

. `transfer_histogram`:
  - Normalização de imagens em fotografia, edição ou aprendizado de máquina, ajustando condições de iluminação.


## Classe `Transformation`

O código abaixo tem como objetivo redimensionar uma imagem utilizando uma proporção especificada.

---

## Bibliotecas e Pacotes Importados

- **skimage.transform:**  
  Este é um submódulo da biblioteca `scikit-image`, que oferece funcionalidades para processamento de imagens. O método `resize` é utilizado para redimensionar imagens, ajustando sua dimensão (altura e largura). Ele também possui parâmetros como `anti_aliasing`, que ajuda a suavizar os artefatos visuais no processo de redimensionamento.

---

## Explicação do Código

### 1. **Definição da Função**
A função `resize_image(image, proportion)` recebe dois argumentos:  
- **`image`:** Uma matriz representando a imagem (geralmente um array NumPy onde cada elemento representa um pixel).  
- **`proportion`:** Um valor decimal (entre 0 e 1) que indica a proporção de redimensionamento. Por exemplo:
  - `proportion = 0.5`: Reduz a imagem pela metade.  
  - `proportion = 1.0`: Mantém a imagem no tamanho original.  

---

### 2. **Validação da Proporção**
- A linha `assert 0 <= proportion <= 1` garante que o valor da proporção esteja dentro do intervalo válido.  
  Caso contrário, uma mensagem de erro será exibida: **"Specify a valid proportion between 0 and 1."**

---

### 3. **Cálculo da Nova Dimensão**
- A altura da imagem é calculada multiplicando o número de linhas (`image.shape[0]`) pela proporção e arredondando o valor.
- A largura é calculada de forma semelhante, multiplicando o número de colunas (`image.shape[1]`) pela proporção.

---

### 4. **Redimensionamento**
- A função `resize` da biblioteca `skimage.transform` é usada para redimensionar a imagem.
- O parâmetro `anti_aliasing=True` melhora a qualidade da imagem, reduzindo ruídos ou efeitos indesejados durante o redimensionamento.

---

### 5. **Retorno da Imagem Redimensionada**
- Após o processamento, a imagem redimensionada é retornada pela função.

---

## Aplicações Práticas

Esse código é útil para ajustar o tamanho de imagens em:
- Projetos de visão computacional.  
- Aplicativos de processamento de imagens.  
- Qualquer aplicação onde diferentes tamanhos de imagem são necessários.

  
