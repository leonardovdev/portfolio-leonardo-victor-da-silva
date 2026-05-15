🛠️ Laboratório de Algoritmos e Estruturas de Controle em Python
📝 Descrição do Projeto
Este repositório reúne um conjunto de scripts utilitários desenvolvidos em Python voltados para simulações do cotidiano comercial, financeiro, acadêmico e climático. O objetivo principal é aplicar de forma prática estruturas de repetição determinísticas e condicionais, manipulação e conversão de tipos de dados (int, float), tratamento normativo de exceções com blocos try/except e ramificações de tomada de decisão.

Desenvolvido como parte das atividades da faculdade de Análise e Desenvolvimento de Sistemas (2026.1), os algoritmos resolvem problemas clássicos de lógica, estruturando entradas dinâmicas dadas por usuários e fornecendo saídas limpas e formatadas.

🚀 Módulos do Sistema
O projeto é segmentado em quatro funções independentes e especializadas:

1. Sistema de Checkout com Desconto Progressivo (processar_vendas)
Simula uma frente de caixa dinâmica que coleta o preço e a quantidade de diferentes tipos de produtos fornecidos pelo operador.

Lógica de Negócio: Aplica um sistema de descontos progressivos sobre o valor bruto acumulado:

10% de desconto se o montante total ultrapassar R$500.00.

5% de desconto se o montante total for maior que R$200.00.

Mecanismo de Resiliência: Caso o operador insira valores nulos ou negativos, o sistema invalida a inserção. Se houver falha de digitação, o bloco try/except pula o item afetado sem interromper a soma total das demais compras.

2. Relatório de Monitoramento Climático (analisar_clima)
Coleta as temperaturas diárias ao longo de um ciclo fechado de uma semana (7 dias) para traçar análises estatísticas e operacionais sobre as variações térmicas de uma região.

Análise de Dados: Computa e exibe a média aritmética simples da semana.

Gatilhos de Segurança: Contabiliza dias de calor intenso (acima de 35°C) e dispara alertas críticos na tela caso temperaturas extremas e perigosas no ambiente (maiores que 45°C ou menores que -5°C) sejam atingidas.

3. Gestor de Notas Acadêmicas (sistema_notas_turma)
Ferramenta para automatizar a avaliação de desempenho de salas de aula, processando o nome e as duas principais notas de cada estudante de maneira sequencial.

Métricas de Classificação: Calcula a média semestral e categoriza os discentes instantaneamente em três estados possíveis:

🟢 Aprovado: Média superior ou igual a 7.0.

🟡 Recuperação: Média entre 5.0 e 6.9.

🔴 Reprovado: Média abaixo de 5.0.

4. Simulador de Investimento com Aportes (simulador_poupanca)
Algoritmo voltado à educação financeira que projeta a evolução de um patrimônio com base em juros compostos mensais acumulados.

Aportes Mensais: Permite ao usuário simular a injeção de novos depósitos de capital a cada ciclo de tempo.

Gatilho de Conquistas: Apresenta um rastreador de metas inteligente que parabeniza o investidor no exato mês em que o saldo acumulado total ultrapassa a barreira dos R$10.000,00 pela primeira vez.

💻 Tecnologias Utilizadas
Linguagem: Python 3.10+

Paradigmas: Programação Estruturada e Funcional

Recursos Nativos: Tratamento de erros (ValueError), Formatação de strings (f-strings), Estruturas de laço (for, range)

📊 Resultados e Aprendizados
O desenvolvimento deste laboratório consolidou competências essenciais de engenharia de software básicas:

Prevenção de Quebras de Fluxo: Implementação rigorosa de tratamento de erros para dados mal formatados informados no console.

Uso de Flags Condicionais: Utilização de variáveis lógicas (Booleanas) para memorizar estados e prevenir a repetição desnecessária de impressões (como o alerta de meta atingida nos investimentos).

Modularização: Divisão de comportamentos em escopos e blocos de funções isoladas, facilitando a reutilização do código.
