# 🌿 Sistema Analisador de Microclima e Conforto Urbano

## 📝 Descrição do Projeto

Este projeto consiste em um algoritmo de monitoramento ambiental focado na avaliação das condições climáticas e da qualidade do ar em diferentes pontos de uma região. O objetivo principal é automatizar o cálculo de um **Índice de Conforto Urbano**, auxiliando no mapeamento de ilhas de calor e na identificação de áreas críticas que afetam o bem-estar da população.

Desenvolvido como parte das atividades práticas do curso de **Análise e Desenvolvimento de Sistemas**, o sistema analisa dinamicamente matrizes bidimensionais com registros de temperatura, umidade relativa e o Índice de Qualidade do Ar (IQA). Através de uma lógica de penalização progressiva baseada em faixas ideais estabelecidas por órgãos de saúde, o software classifica a qualidade do ar em níveis e gera uma nota final de conforto para cada local avaliado.

---

## 🚀 Módulos e Lógica do Sistema

O algoritmo processa os dados de maneira sequencial através de estruturas de controle bem definidas:

### 1. Classificação do IQA (Índice de Qualidade do Ar)

O sistema avalia a concentração de poluentes (IQA) e categoriza a situação do ambiente através de ramificações condicionais encadeadas (`if/elif/else`):

* 🟢 **Boa:** IQA até 50.
* 🟡 **Moderada:** IQA entre 51 e 100.
* 🟠 **Ruim:** IQA entre 101 e 150.
* 🔴 **Muito ruim:** IQA acima de 150.

### 2. Algoritmo de Penalização por Conforto

Cada local inicia com uma nota de conforto máxima padrão (Nota 10). O script então aplica decréscimos de acordo com o nível de estresse térmico e respiratório detectado:

* **Temperatura:** Locais que ultrapassam 32°C ou ficam abaixo de 18°C perdem **3 pontos** devido ao estresse térmico severo. Ambientes acima de 28°C sofrem uma penalização leve de **1 ponto**.
* **Umidade:** Níveis críticos de ar extremamente seco (abaixo de 30%) ou excessivamente úmido (acima de 80%) reduzem a nota em **2 pontos**.
* **Qualidade do Ar:** Um IQA acima de 100 penaliza o local em **3 pontos**, enquanto um índice moderado (acima de 50) desconta **1 ponto**.
* **Normalização:** Uma trava lógica garante que a pontuação nunca seja negativa, definindo o piso mínimo em `0`.

---

## 💻 Tecnologias Utilizadas

* **Linguagem:** Python 3.10+
* **Estruturas de Dados:** Listas Compostas (Matrizes Dinâmicas)
* **Paradigmas:** Programação Estruturada e Computação Científica Básica

---

## 📊 Resultados e Aprendizados

A implementação deste laboratório de análise microclimática consolidou conceitos fundamentais para o desenvolvimento de soluções voltadas a *Smart Cities* (Cidades Inteligentes):

* **Manipulação de Arrays Multidimensionais:** Aprendizado prático na extração e mapeamento de dados indexados sequencialmente a partir de coleções aninhadas.
* **Sistemas de Pontuação Baseados em Regras:** Modelagem de algoritmos de ranqueamento que transformam múltiplos fatores qualitativos e quantitativos em uma única métrica clara de tomada de decisão.
* **Clean Code e Interpolação:** Uso correto de *f-strings* para a geração de relatórios limpos, organizados e formatados diretamente via console para o usuário final.

---

## 🔧 Como Executar

1. Certifique-se de possuir o Python instalado no sistema.
2. Clone este repositório para o seu computador.
3. Execute o script principal utilizando o terminal para visualizar o relatório gerado:
```bash
python main.py

```
