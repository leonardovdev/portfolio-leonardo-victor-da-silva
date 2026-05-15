# 🛒 Sistema Automatizado de Frente de Caixa (PDV)

## 📝 Descrição do Projeto

Este projeto consiste no desenvolvimento da lógica algorítmica completa para um sistema automatizado de Ponto de Venda (PDV/Frente de Caixa). O objetivo principal é estruturar um fluxo robusto que abranja desde o registro sequencial de produtos até o processamento financeiro de pagamentos e a distribuição otimizada do troco em cédulas comerciais.

Desenvolvido como parte do currículo de **Análise e Desenvolvimento de Sistemas (2026.1)**, o sistema foi modularizado em três rotinas lógicas principais para garantir a integridade dos dados e uma experiência fluida:

1. 
**Registro de Itens:** Acumulação iterativa dos valores das mercadorias passadas pelo cliente.


2. 
**Validação de Pagamentos:** Verificação se o montante fornecido em dinheiro cobre o total devido, tratando exceções de valores insuficientes.


3. 
**Distribuição Otimizada de Troco:** Algoritmo guloso para calcular e entregar a menor quantidade possível de cédulas ao cliente.



---

## 🚀 Módulos e Lógica do Sistema

### 1. Registro de Compras (`RegistrarCompra`)

Esta rotina é responsável por inicializar o caixa e abrir um loop interativo para computar os produtos. O sistema solicita o preço de cada item inserido, adiciona o valor ao montante acumulado e questiona o operador se há mais mercadorias a serem registradas antes de fechar a conta.

* 
**Entradas:** Preço de cada item individual.


* 
**Controle de Fluxo:** Repetição condicional executada até que a resposta do usuário seja "N" (Não).


* 
**Saída:** Retorna o valor consolidado da compra (`Total_compra`).



### 2. Validação Financeira (`ValidarPagamento`)

Após a consolidação do valor, este submódulo recebe o montante total e realiza a leitura da quantia fornecida em dinheiro pelo comprador.

* 
**Tratamento de Erro:** Caso o valor pago seja menor que o total da compra, o sistema emite um alerta de "Valor Insuficiente" e impede o encerramento até que a pendência seja sanada.


* 
**Sucesso na Operação:** Se o valor for suficiente, calcula-se a diferença e exibe-se o valor total que deve ser devolvido.



### 3. Divisor de Cédulas (`DistribuirNotas`)

Responsável pela inteligência da devolução do troco. Com base no valor obtido no passo anterior, o algoritmo varre uma lista decrescente de cédulas padrão disponíveis no mercado brasileiro: `[100, 50, 20, 10, 5, 2]`.

* 
**Cálculo da Divisão:** Para cada cédula da lista, o sistema extrai a divisão inteira para saber quantas notas daquele valor específico cabem no troco atual.


* 
**Atualização do Restante:** O resto da divisão vira o novo saldo a ser avaliado pela próxima nota da lista.


* 
**Saída:** Informa ao operador exatamente quais e quantas cédulas devem ser entregues em mãos.



---

## 🛠️ Tecnologias Utilizadas

* 
**Linguagem de Modelagem:** Pseudocódigo (Visualg / Portugol) 


* 
**Arquitetura de Fluxo:** Engenharia de Software e Diagramação de Processos 


* **Ambiente de Desenvolvimento:** Editores de texto compatíveis com Markdown para documentação técnica do GitHub

---

## 📊 Resultados e Aprendizados

O desenvolvimento e a abstração destes algoritmos permitiram sedimentar competências fundamentais da análise estruturada de sistemas:

* 
**Estruturas de Repetição Controladas:** Uso eficiente de loops pós-testados (`Repetir... Até que`) para interações dinâmicas com usuários finais.


* 
**Otimização de Algoritmos (Greedy Approach):** A aplicação da lógica gulosa na distribuição de cédulas provou-se altamente eficiente para resolver problemas reais de logística de caixa e trocos rápidos.


* 
**Tratamento e Prevenção de Falhas:** Desenvolvimento de barreiras lógicas para impedir que o sistema finalize transações comerciais em prejuízo (validação de saldo mínimo).



---

## 🔧 Como Executar os Algoritmos

1. Clone este repositório em sua máquina local.
2. Abra um interpretador de pseudocódigo de sua preferência (como o *Visualg*).
3. Copie o código fonte contido na pasta `/src` correspondente ao módulo desejado.
4. Execute o programa pressionando `F9` ou o comando equivalente do interpretador e simule a passagem de uma compra no terminal de testes.
