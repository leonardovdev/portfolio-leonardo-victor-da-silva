# 🎨 Desenhando Emojis e Matrizes com Dados

### Engenharia de Dados Aplicada à Computação Visual e Sonora

> "Dados são apenas números — até você ensiná-los a desenhar."

!([https://api.together.xyz/v1/images/generations](https://www.google.com/search?q=https://api.together.xyz/v1/images/generations))

---

## 📌 Sobre o Projeto

Este projeto explora a manipulação profunda de estruturas de dados aninhadas em Python para processar imagens e áudio representados por matrizes numéricas.

O objetivo central é demonstrar que, por trás de qualquer elemento digital, existe matemática pura. Utilizando os algoritmos corretos, transformamos dicionários e listas brutas em representações visuais e sonoras completas.

### 📦 O Fluxo de Transformação do Dado

```
Dado Bruto (Número) 
       ↓ 
Matriz Numérica (Lista de Listas) 
       ↓ 
Pixel Colorido (Canais RGB) 
       ↓ 
Imagem Renderizada (plt.imshow)

```

---

## 🚀 Desafios e Funcionalidades

### 🟥 Desafio 1: Processamento de Emojis RGB (Filtro de Sombreamento)

Neste desafio, aplicamos um filtro de sombreamento em imagens vetorizadas dentro de dicionários, navegando por três níveis de profundidade estrutural: `Dicionário → Linhas → Pixels`.

```python
for emoji, linhas in emojis.items():
    for linha in linhas:
        for pixel in linha:
            pixel[0] //= 2  # Canal R (Vermelho)
            pixel[1] //= 2  # Canal G (Verde)
            pixel[2] //= 2  # Canal B (Azul)

```

* **O que faz:** Reduz a intensidade de cada canal de cor pela metade, simulando um efeito de sombra/pós-processamento realista sobre os emojis através de divisão inteira (`//=`).

### 🟦 Desafio 2: Transposição de Matrizes Musicais

Reorganização de frequências sonoras mudando a perspectiva dos dados de colunas para linhas.

* **De:** Instrumento $\rightarrow$ `[frequência_por_tempo]`
* **Para:** Tempo $\rightarrow$ `[frequência_por_instrumento]`

```python
matriz_transposta = list(map(list, zip(*matriz_original)))

```

* **O que faz:** Transpõe a matriz de dados para permitir que a biblioteca musical seja lida em eixos diferentes — o equivalente matemático a ler uma partitura verticalmente em vez de horizontalmente.

### 🟩 Desafio 3: Edição Dinâmica de Pixels em Tempo Real

Manipulação direta em memória de listas mutáveis para edição cirúrgica de pixels.

```python
galeria[0].pop(0)                    # Remove o primeiro pixel da linha
galeria[0].insert(2, (0, 0, 255))    # Insere um pixel azul puro na posição 2

```

* **O que faz:** Simula o comportamento interno de ferramentas profissionais de edição de imagem (como o Adobe Photoshop), alterando a estrutura da matriz gráfica em tempo de execução via código puro.

---

## 🧠 Conceitos Computacionais Aplicados

| Conceito | Aplicação Prática no Projeto |
| --- | --- |
| **Iteração Multicamadas** | Navegação em estruturas de dicionários com 3 níveis de profundidade. |
| **Tuplas e Listas Aninhadas** | Modelagem estrutural dos canais RGB por pixel. |
| **Transposição Matricial** | Reorganização de eixos para leitura de frequências musicais. |
| **Métodos de Lista** | Uso de `.pop()` e `.insert()` para mutação de dados em tempo real. |
| **Visualização de Dados** | Renderização matricial com `plt.imshow()` do Matplotlib. |
| **Operadores Aritméticos** | Manipulação direta de matrizes numéricas para ajuste de brilho e cor. |

---

## 🛠️ Tecnologias Utilizadas

* **Linguagem:** Python
* **Visualização:** Matplotlib
* **Ambientes:** Google Colab / Jupyter Notebook

---

## 🚀 Como Executar o Projeto

### Pré-requisitos

Certifique-se de ter o Matplotlib instalado no seu ambiente:

```bash
pip install matplotlib

```

### Opção 1: Google Colab (Recomendado)

1. Acesse [colab.research.google.com]().
2. Faça o upload do arquivo `.py` ou `.ipynb`.
3. Execute as células sequencialmente para visualizar os gráficos gerados.

### Opção 2: Ambiente Local (VS Code / Terminal)

Clone o repositório do projeto:

```bash
git clone https://github.com/gui995/portfolio-guilherme-henrique-souza-goncalves

```

Acesse o diretório:

```bash
cd projeto-desenhando-emojis-com-dados

```

Execute o script:

```bash
python projeto_desenhando_emojis_com_dados.py

```

---

## 💡 Principais Aprendizados

* **Domínio de Estruturas Complexas:** Habilidade para navegar e extrair valor de dados com mais de 3 níveis de profundidade.
* **Pensamento Matricial:** Compreensão prática de que imagens e áudios são matrizes multidimensionais — o fundamento essencial para Visão Computacional e IA.
* **Validação Visual:** Capacidade de traduzir lógica abstrata de código em outputs visuais claros usando `matplotlib`.
