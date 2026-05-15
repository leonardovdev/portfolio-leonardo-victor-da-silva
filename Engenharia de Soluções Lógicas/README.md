# 🌾 Sistema Automatizado de Irrigação Inteligente

## 📝 Descrição do Projeto
Este projeto consiste no desenvolvimento do fluxo lógico e algorítmico para um sistema automatizado de irrigação inteligente guiado por sensores. O objetivo principal é otimizar o uso da água, garantindo que o solo receba a quantidade ideal de rega com base em medições em tempo real, além de contar com mecanismos de segurança contra vazamentos ou anomalias no fluxo.

Desenvolvido como parte das disciplinas do curso de **Análise e Desenvolvimento de Sistemas**, o sistema realiza a leitura de sensores de umidade e fluxo, processa as tomadas de decisão condicionais para ativação da bomba d'água e monitora continuamente o estado do ambiente até que as condições ideais sejam atingidas.

## 📊 Fluxograma do Sistema
A lógica de controle descrita na documentação do projeto segue as seguintes etapas estruturadas:

1. **Início & Leitura:** O sistema inicia o ciclo e realiza a ação de `Ler Sensores`.
2. **Validação de Umidade:** * Se a **Umidade do Solo** estiver adequada (**Sim**): O sistema aciona o estado `Não Irrigar` e encerra o processo (`Fim`).
   * Se a umidade estiver baixa (**Não**): O sistema avança para `Calcular Quantidade d'Água` e em seguida executa o comando `Ativar Irrigação`.
3. **Mecanismo de Segurança (Fluxo):**
   * Durante a irrigação, o sistema checa se o **Fluxo está Acima do Limite**.
   * Se estiver acima (**Sim**): O sistema executa as ações de `Emitir Alerta`, depois `Desligar Irrigação` e encerra o fluxo (`Fim`) para evitar desperdícios ou alagamentos por quebra de cano.
   * Se o fluxo estiver normal (**Não**): O sistema segue para a próxima validação.
4. **Monitoramento e Fechamento:**
   * O sistema avalia se **Atingiu a Umidade Ideal**.
   * Se **Não** atingiu: O fluxo entra em looping e executa o comando de `Voltar ao Monitoramento`.
   * Se **Sim** (atingiu a umidade esperada): O sistema avança para `Desligar Irrigação` e conclui a execução com sucesso (`Fim`).

## 🚀 Tecnologias Utilizadas
* **Linguagem de Simulação:** Python 3.10 / C++ (Arduino)
* **Modelagem de Processos:** Desenho Técnico de Algoritmos e Fluxogramas
* **Hardware Alvo (Referência):** Sensores de Umidade de Solo (Higrômetro), Sensores de Fluxo de Água, Relés e Microcontroladores (Arduino/ESP32)

## 📊 Resultados e Aprendizados
A estruturação deste algoritmo permitiu consolidar conceitos fundamentais de lógica de programação e arquitetura de sistemas orientados a IoT (Internet das Coisas).
* **Automação Eficiente:** Eliminação do fator humano na decisão de rega através do cálculo dinâmico de necessidade hídrica.
* **Tratamento de Anomalias:** Aprendizado prático sobre como implementar rotinas de interrupção e segurança (checagem de fluxo limite).
* **Estruturas de Repetição (Loops):** Aplicação real de feedback contínuo em sistemas fechados (Looping de monitoramento).

## 🔧 Como Executar
1. Clone o repositório.
2. Certifique-se de ter o interpretador ou simulador de hardware configurado.
3. Execute o comando de simulação da lógica: `python main.py`
