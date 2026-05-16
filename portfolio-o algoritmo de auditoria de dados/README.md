# 🔍 Sistema de Auditoria de Dados e Análise de Risco Financeiro

## 📝 Descrição do Projeto

Este projeto consiste em um algoritmo automatizado focado em auditoria e inteligência financeira. O objetivo principal é analisar transações comerciais brutas, calcular métricas de faturamento e identificar discrepâncias críticas (*outliers*) para mitigar fraudes e anomalias de preenchimento que afetam os relatórios gerenciais.

Desenvolvido como parte das atividades práticas do curso de **Análise e Desenvolvimento de Sistemas**, o sistema monitora lançamentos operacionais utilizando regras de negócio adaptáveis. Ele define margens de tolerância e traça uma linha base média dinâmica capaz de isolar "ruídos" estatísticos ou valores artificialmente inflados, disparando rotinas automáticas de quarentena e sugerindo revisões manuais se detectar dados em desconformidade.

---

## 🚀 Módulos e Lógica do Sistema

O motor de auditoria executa um ciclo estruturado em etapas essenciais de processamento de dados:

### 1. Entrada Dinâmica e Casting Resiliente

* 
**Sanitização de Strings:** O sistema intercepta o valor imputado pelo operador em formato texto, tratando erros comuns de digitação ao substituir separadores regionais de milhar/decimal (`replace(',', '.')`).


* 
**Tratamento de Exceções:** Implementação estruturada de loops condicionais e blocos `try/except` capturando falhas do tipo `ValueError`. Caso uma entrada seja considerada inválida, o terminal avisa o usuário e repete o prompt sem quebrar a pilha de execução do programa.



### 2. Análise de Vendas e Detecção de Discrepâncias (`analisar_vendas`)

* 
**Cálculo de Média Dinâmica:** Avalia lotes de transações gerando uma média aritmética que serve como ponto de partida comparativo.


* 
**Gatilho de Isolamento (Filtro de Outliers):** O script implementa uma varredura que avalia se alguma transação pontual excede em 5 vezes ou mais a média calculada do lote. Ao identificar essa discrepância, o algoritmo sinaliza o registro como suspeito (`discrepancia_detectada = True`) e emite um comando explícito para **Revisão Manual**.


* 
**Travas de Quarentena:** Caso a média global do lote supere o teto padrão pré-definido pelo negócio (`LIMITE_SEGURANCA`), o sistema bloqueia preventivamente o lote exibindo o status: `ALERTA: SISTEMA EM QUARENTENA!`.



---

## 🛠️ Tecnologias Utilizadas

* 
**Linguagem:** Python 3.10+ 


* 
**Tipagem de Dados Aplicada:** Coleções Dinâmicas (`lists`), Decimais de Precisão (`float`) e Strings 


* 
**Paradigmas:** Programação Estruturada e Engenharia de Software Segura 



---

## 📊 Resultados e Aprendizados

O desenvolvimento deste projeto laboratorial proporcionou o aprendizado prático de conceitos fundamentais para a rotina de um analista de sistemas:

* 
**O Perigo do Escopo Global:** Análise crítica sobre o uso de variáveis globais (`global LIMITE_SEGURANCA`). Foi absorvido que, em ambientes bancários de produção reais, expor limites estruturais de forma aberta cria sérias vulnerabilidades de segurança, sendo indispensável a aplicação de técnicas de encapsulamento.


* 
**Normalização de Dados:** Compreensão profunda de como os extremos distorcem amostras reais e da importância de remover ruídos antes de expor relatórios estatísticos para tomadas de decisão gerenciais.


* 
**Sintaxe e Indentação Rígida:** Fixação da premissa de que a indentação no Python vai muito além da estética visual; ela define as regras e limites lógicos de escopo e funcionamento do código (`IndentationError`).



---

## 🔧 Como Executar

1. Certifique-se de ter o Python 3.10 ou superior instalado em seu ambiente.


2. Clone este repositório para o seu diretório local.
3. Certifique-se de que a estrutura de blocos e recuos de 4 espaços está correta para evitar travamentos.


4. Execute o validador principal via console com o comando:
```bash
python auditoria_vendas.py

```
