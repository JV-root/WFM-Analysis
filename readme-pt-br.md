# 📊 Análise de WFM – Desempenho de Call Center (Outubro de 2020)

> 🌐 [Read this in English](readme.md)

## 📌 Visão Geral

Este projeto apresenta uma análise de dados ponta a ponta da operação de um call center durante outubro de 2020, com foco no desempenho do Acordo de Nível de Serviço (SLA), na distribuição da demanda e na experiência do cliente.

O notebook tem duas partes. A **Parte 1** preserva a primeira análise, com as conclusões exatamente como foram escritas. A **Parte 2** submete cada uma dessas conclusões a testes estatísticos e refaz o diagnóstico a partir dos resultados.

---

## 🎯 Objetivos

A análise foi desenhada para responder a perguntas operacionais centrais:

- Em que patamar está o SLA e qual é a distância em relação à meta?
- O gap é explicado por alguma dimensão mensurável (call center, canal, motivo ou dia da semana)?
- O desempenho operacional se traduz na experiência do cliente?
- Como a demanda se compõe, e onde estão as alavancas para reduzi-la?
- O que esta base **não** permite concluir, e qual dado seria necessário obter?

---

## 📂 Base de Dados

- Fonte: dados de call center (base simulada, obtida no Kaggle)
- Período: outubro de 2020, com 30 dias analisados (31/10 excluído por ter apenas 1 registro)
- Volume: 32.941 registros, ~1.100 por dia
- Principais atributos:
  - Status de SLA (Dentro / Abaixo / Acima)
  - Localidade do call center
  - Canal de entrada (voz, chatbot, e-mail, web)
  - Sentimento
  - Nota de CSAT (cobertura de 37,3% dos contatos)
  - Duração da chamada (AHT)
  - Motivo do contato (incluindo indisponibilidades de serviço)

---

## 🧠 Abordagem Analítica

A análise segue esta estrutura:

1. **Preparação dos dados**
2. **Parte 1: análise original, preservada**
3. **Parte 2: revisão com testes de hipótese** (auditoria de qualidade dos dados, aderência, distribuição, experiência e forma das métricas)
4. **Recomendações**, separadas entre o que não fazer e o que fazer com os dados disponíveis
5. **Conclusão**, em camadas: o que a operação mostra, o que a base não permite e o teto do diagnóstico

A regra central da Parte 2 é testar antes de concluir: cada afirmação causal vem acompanhada do teste que a sustenta ou a derruba.

---

## 🔎 Principais Conclusões

- **O gap é de patamar, não de evento.** A aderência ao SLA foi de 75,3%, 4,7pp abaixo da meta de 80%, e a variação diária cabe quase toda no ruído amostral.
- **Nenhuma dimensão disponível explica o gap.** Call center, canal, motivo e dia da semana não são significativos a 5%.
- **O SLA não se traduz em experiência.** O CSAT dentro e fora do SLA é estatisticamente idêntico (5,53 contra 5,56).
- **A demanda tem estrutura clara.** Dúvidas de fatura somam 71,2% do volume. Indisponibilidade, apontada na Parte 1 como principal motivador, é o menor dos três motivos (14,4%) e nunca chega por voz.
- **A base tem limites sérios.** O AHT segue uma distribuição uniforme entre 5 e 45 minutos, sem agentes, escalas nem granularidade de hora. O diagnóstico de capacidade não pode ser fechado com estes dados.

---

## 🛠️ Stack Técnica

- Python
- Pandas
- NumPy
- Matplotlib
- Testes estatísticos: qui-quadrado, intervalos de confiança de 95% e t de Student

---

## 📈 Padrões de Visualização

O projeto aplica boas práticas de visualização de dados:

- Normalização de séries temporais (intervalo de datas completo)
- Distribuições percentuais para permitir comparabilidade
- Intervalos de confiança de 95% em comparações entre grupos
- Diferenciação visual entre série em destaque e séries secundárias
- Rotulagem direta nas séries (legenda apenas para linhas de referência e categorias)
- Design minimalista (sem bordas superior e direita)
- Títulos e subtítulos em estilo executivo
- Indicação explícita de fonte e período

---


## 👤 Autor

**João Lima**

- Cientista de Dados | Performance & Operações
- Foco em WFM, otimização de SLA e analytics operacional

---
