# 🎮 Xbox Game Pass — Dashboard Financeiro

![Version](https://img.shields.io/badge/version-v1.0.0-brightgreen)
![Status](https://img.shields.io/badge/status-portfolio-blue)
![Excel](https://img.shields.io/badge/built%20with-Excel-217346)

### 📝 Release Highlights
* Projeto de portfólio focado em **modelagem financeira e análise de dados em Excel**.
* Estrutura modular em quatro abas: **Assets**, **Bases**, **Cálculos** e **Dashboard**.
* Regras de negócio automatizadas para **precificação, descontos e projeção de receita**.
* Projeção de faturamento anual baseada na data de início das assinaturas.

---

## 👁️ Visão Geral
_Este projeto é uma **dashboard financeira em Excel** desenvolvida como item de portfólio para demonstrar competências em:_
* 📊 Estruturação de bases de dados
* 🧮 Lógica de negócios com fórmulas
* 📈 Visualização de indicadores
* 💼 Organização de projetos analíticos
O objetivo é simular um cenário de assinaturas do **Xbox Game Pass**, consolidar dados de usuários e projetar a receita anual de 2025.

---

## 🗂️ Estrutura do Arquivo
### 🎨 1. Aba `Assets`
_**Finalidade:** Identidade visual do projeto._
* 🎨 Paleta de cores e padrões visuais.
* 🖼️ Espaço para ícones e elementos gráficos.

> Aba dedicada apenas ao design e organização visual.

---

### 📊 2. Aba `Bases`
_**Finalidade:** Base de dados principal._
**Campos:**
* 🆔 **ID de Assinatura do Usuário**
* 👤 **Nome do Assinante**
* 🧾 **Plano** (*Ultimate*, *Premium*)
* 📅 **Data de Início**
* 🔁 **Renovação Automática (Sim/Não)**

**Campos calculados:**
* 💰 **Preço Base (F)**
* 🏷️ **Desconto (G)**
* 🧮 **Total Mensal (H)**

#### ⚙️ Regras de Negócio
* **Preço por Plano:**
  * 🎯 *Ultimate* → R$ 119,90
  * ⭐ *Premium* → R$ 59,90
    
* **Desconto por Renovação:**
  * 🎯 *Ultimate + Renovação* → R$ 20,00
  * ⭐ *Premium + Renovação* → R$ 10,00
  * ❌ *Ultimate + Sem renovação* → R$ 5,00
  * ❌ *Premium + Sem renovação* → R$ 0,00

---

### 🧮 3. Aba `Cálculos`
_**Finalidade:** Camada de modelagem financeira._
_Para cada usuário:_
* 📆 Cálculo da quantidade de meses ativos em 2025.
* 💵 Projeção da receita total por assinatura.

**Regra principal:**
* Se a **data de início** for posterior a **31/12/2025**, a receita é **zero**.
* Caso contrário, a receita é o número de meses ativos multiplicado pelo **valor mensal final**.

---

### 📈 4. Aba `Dashboard`
_**Finalidade:** Apresentação visual dos resultados._
_Inclui:_
* 🏷️ Título do projeto
* 👋 Mensagem de boas-vindas
* 📊 Consolidação da receita anual calculada

> Foco em comunicação visual e leitura executiva.

---

## 🧾 Fórmulas Utilizadas
_Este projeto utiliza exclusivamente funções nativas do Excel para demonstrar lógica e clareza de modelagem:_
### 🔁 `IF()` (SE)
```excel
=IF(C83="Ultimate",119.9,IF(C83="Premium",59.9))
```

### 🔗 `AND()` (E)
```excel
=IF(AND(C83="Ultimate",E83="Sim"),20,IF(AND(C83="Premium",E83="Sim"),10,0))
```

### ➕ `SUM()` (SOMA)
```excel
=SUM(F83-G83)
```

### 📅 `DATE()` (DATA)
```excel
DATE(2025,12,31)
```

### 📆 `YEAR()` (ANO) e 🗓️ `MONTH()` (MÊS)
```excel
((YEAR(DATE(2025,12,31))-YEAR(Bases!D95))*12 + (MONTH(DATE(2025,12,31))-MONTH(Bases!D95)) + 1)
```

### 💼 Receita Anual por Assinatura
```excel
=IF(Bases!D95>DATE(2025,12,31),0,
((YEAR(DATE(2025,12,31))-YEAR(Bases!D95))*12 + (MONTH(DATE(2025,12,31))-MONTH(Bases!D95)) + 1) * Bases!H95)
```

---

## ▶️ Como Usar
1. Abra o arquivo Excel.
2. Edite apenas a aba **Bases** (que está oculta):
   * ✍️ Adicione ou altere usuários
   * 🧾 Escolha o plano
   * 📅 Defina a data de início
   * 🔁 Informe se há renovação
3. 📊 Acompanhe os resultados automaticamente na aba **Dashboard**.

---

## 🎯 Objetivo de Portfólio
_Este projeto demonstra:_
* Capacidade de estruturar dados
* Aplicação de regras de negócio
* Construção de modelos financeiros
* Comunicação visual por meio de dashboards

_Ideal para vagas em **Análise de Dados, BI, Finanças e Planejamento**._

---
