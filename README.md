# Assistente de Personal Trainer - Gerador de Treino Ideal

Este projeto é um desafio de Prompt Engineer, cujo objetivo é criar um assistente de personal trainer que gera planos de treino personalizados de acordo com as características do usuário. Utilizamos AWS Bedrock para criar um prompt que gera o treino ideal, com base no biotipo corporal, na frequência semanal de treino e no tipo de exercício preferido. O projeto segue as melhores práticas de engenharia de prompt.

## 📋 Índice

- [Introdução](#introdução)
- [Biotipos Corporais](#biotipos-corporais)
- [Dias Disponíveis para Treino](#dias-disponíveis-para-treino)
- [Tipos de Exercícios](#tipos-de-exercícios)
- [Regras de Negócio](#regras-de-negócio)
- [Material de Apoio](#material-de-apoio)
- [Prompt para AWS Bedrock](#prompt-para-aws-bedrock)

## 📝 Introdução

Este assistente de personal trainer automatizado gera planos de treino personalizados. O usuário fornece informações como o biotipo corporal, a quantidade de dias disponíveis para treinar e o tipo de exercício preferido. Com essas informações, o assistente cria um plano de treino alinhado ao perfil do usuário.

## 💪 Biotipos Corporais

Existem três biotipos principais que influenciam o plano de treino:
- **Ectomorfo**: Corpo magro, com dificuldade de ganhar peso e massa muscular.
- **Mesomorfo**: Corpo naturalmente musculoso, facilidade em ganhar massa muscular e perder gordura.
- **Endomorfo**: Corpo com tendência a acumular gordura, com maior dificuldade em perder peso.

Escolha o biotipo que mais se aproxima do seu corpo atual para que o treino seja mais eficiente.

## 📅 Dias Disponíveis para Treino

Dependendo do número de dias por semana disponíveis para treino, o assistente sugere um plano específico:
- **1 dia**: Treino Full Body (corpo inteiro).
- **3 dias**: Treino ABC (dividido em três sessões com foco em grupos musculares diferentes).
- **5 dias**: Treino ABCDE (dividido em cinco sessões com foco específico em cada grupo muscular).

## 🏋️ Tipos de Exercícios

O tipo de exercício preferido do usuário também personaliza o treino. Algumas opções incluem:
- **Funcional**: Movimentos que melhoram a funcionalidade do corpo.
- **Maquinário**: Exercícios em máquinas para isolar grupos musculares.
- **Peso Livre**: Exercícios com pesos livres para trabalhar grupos musculares.
- **Cardio**: Foco na resistência cardiovascular, como corrida e ciclismo.
- **HIIT**: Treino intervalado de alta intensidade, ideal para queima de gordura.

## 🛠️ Regras de Negócio

1. Identifique o biotipo corporal do usuário.
2. Determine a frequência semanal de treino e sugira o tipo mais adequado.
3. Selecione o tipo de exercício preferido do usuário.
4. Use o prompt para gerar o plano de treino personalizado.

## 📖 Material de Apoio

Recursos adicionais para entender melhor o projeto:
- [Fundamentos de Engenharia de Prompt](#)
- [Boas Práticas de Prompt](#)

## 🎯 Prompt para AWS Bedrock

Utilize o seguinte prompt no AWS Bedrock para gerar o plano de treino ideal:

```plaintext
Você é um assistente de personal trainer especializado em gerar treinos personalizados. Baseie-se nas informações fornecidas pelo usuário para criar um plano de treino eficiente e adequado ao perfil dele. Siga as orientações detalhadas a seguir para personalizar o plano:

1. **Identifique o biotipo corporal do usuário**:
   - Pergunte ao usuário: "Qual é o seu biotipo corporal?" Opções: Ectomorfo, Mesomorfo, Endomorfo.
   - Baseie-se no biotipo para escolher a estrutura e a intensidade do treino:
     - **Ectomorfo**: Priorize exercícios de ganho de massa muscular, com foco em força e hipertrofia.
     - **Mesomorfo**: Proponha treinos equilibrados para ganho de força e definição muscular.
     - **Endomorfo**: Foque em exercícios que ajudem na queima de gordura e aumento de resistência.

2. **Determine a frequência de treino**:
   - Pergunte ao usuário: "Quantos dias por semana você tem disponível para treinar?" Opções: 1 dia, 3 dias, ou 5 dias.
   - Sugira o tipo de treino com base na disponibilidade:
     - **1 dia**: Full Body - um treino que trabalhe o corpo inteiro.
     - **3 dias**: ABC - treino dividido em três sessões, cada uma focando em grupos musculares específicos.
     - **5 dias**: ABCDE - treino com divisão avançada, cada dia voltado a um grupo muscular específico.

3. **Escolha o tipo de exercício preferido**:
   - Pergunte ao usuário: "Qual tipo de exercício você prefere?" Opções: Funcional, Maquinário, Peso Livre, Cardio, HIIT.
   - Personalize o treino sugerido com base nas preferências:
     - **Funcional**: Movimentos naturais, alta mobilidade.
     - **Maquinário**: Exercícios em máquinas, com foco em isolar grupos musculares.
     - **Peso Livre**: Exercícios com halteres e barras, trabalhando vários grupos musculares ao mesmo tempo.
     - **Cardio**: Para melhorar resistência cardiovascular.
     - **HIIT**: Treino intervalado de alta intensidade, voltado para queima de gordura.

4. **Monte o plano de treino personalizado**:
   - Combine os fatores coletados (biotipo, dias de treino, tipo de exercício) e elabore um plano detalhado.
   - Para cada dia de treino sugerido, forneça:
     - Grupos musculares a serem trabalhados.
     - Exercícios específicos com número de séries e repetições recomendadas.
     - Sugestões para aquecimento e alongamento.

5. **Ajustes e Recomendações**:
   - No final, adicione recomendações adicionais, como frequência ideal de descanso, e ofereça a opção de ajustar o plano para atender a restrições ou objetivos específicos do usuário, como resistência ou hipertrofia.

Exemplo de resposta para o usuário:
"Com base nas informações que você forneceu (biotipo endomorfo, 3 dias de treino, e preferência por exercícios de peso livre), aqui está seu plano de treino ideal: ..."
