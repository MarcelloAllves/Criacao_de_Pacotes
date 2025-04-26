# Classe `io`

Este código tem duas funções principais relacionadas ao processamento de imagens:
- **Ler uma imagem a partir de um arquivo.**
- **Salvar uma imagem em um caminho específico.**

---

## Bibliotecas e Pacotes Importados

- **skimage.io:** Um submódulo da biblioteca `scikit-image` usado para entrada (leitura) e saída (salvamento) de imagens.
  - **imread:** Lê uma imagem de um arquivo e retorna como uma matriz NumPy.
  - **imsave:** Salva uma matriz de imagem como arquivo no caminho especificado.

---

## Explicação do Código

### 1. Função `read_image`
- **Objetivo:**
  - Ler uma imagem de um arquivo.
- **Argumentos:**
  - `path`: O caminho do arquivo onde a imagem está localizada.
  - `is_gray`: Indica se a imagem deve ser lida em escala de cinza ou em cores (padrão é `False`, ou seja, cores).
- **Funcionamento:**
  - Usa `imread` para carregar a imagem do caminho fornecido.
  - Se `is_gray=True`, a imagem é convertida para escala de cinza automaticamente.
- **Retorno:**
  - A imagem carregada como um array NumPy.

---

### 2. Função `save_image`
- **Objetivo:**
  - Salvar uma matriz de imagem em um arquivo.
- **Argumentos:**
  - `image`: A matriz NumPy representando a imagem a ser salva.
  - `path`: O caminho onde a imagem será salva.
- **Funcionamento:**
  - Usa `imsave` para salvar a imagem no caminho fornecido.
- **Retorno:**
  - Não há valor de retorno. Apenas salva o arquivo no diretório especificado.

---

### Resumo

- A função **`read_image`** é usada para carregar imagens de arquivos, com a opção de convertê-las para escala de cinza.
- A função **`save_image`** salva a matriz de imagem em um arquivo no disco.
- Essas funções são úteis para manipular imagens no contexto de projetos de visão computacional ou processamento de imagens.

---

# Classe `plot`

Este código define três funções para visualização e análise de imagens usando o pacote `matplotlib.pyplot`, que é amplamente utilizado para criar gráficos e visualizações em Python.

---

## Bibliotecas Importadas

- **matplotlib.pyplot:**  
  Biblioteca essencial para criar gráficos e exibir imagens. Ela fornece funcionalidades como `imshow`, `hist` e `subplots`, que permitem personalizar visualizações e criar layouts mais elaborados.

---

## Funções Definidas

### 1. **`plot_image(image)`**
- **Objetivo:** Exibir uma única imagem em escala de cinza.
- **Funcionamento:**
  - Cria uma figura com dimensões de 12 x 4 usando `plt.figure(figsize=(12, 4))`.
  - Exibe a imagem fornecida como entrada com o mapa de cores `'gray'`, que corresponde à escala de cinza.
  - Remove os eixos ao redor da imagem com `plt.axis('off')`.
  - Mostra a imagem usando `plt.show()`.
- **Exemplo de Uso:**
  ```python
  plot_image(minha_imagem)
