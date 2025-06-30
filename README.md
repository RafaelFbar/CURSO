# 📊 Análise de Vendas do Xbox Game Pass com Excel e Inteligência Artificial

Projeto desenvolvido como parte do curso da **DIO - Excel com Inteligência Artificial**, com o objetivo de aplicar recursos avançados do Excel, como Tabelas Dinâmicas, fórmulas e dashboards, para explorar uma base de assinaturas do Xbox Game Pass.

---

## 🧾 Sobre o Projeto

O arquivo `dashboard.xlsx` simula um ambiente empresarial de análise de vendas por assinaturas de planos Xbox Game Pass. Ele inclui dados como:

- Informações dos assinantes (ID, nome, plano, início da assinatura)
- Valor da assinatura e extras adquiridos (EA Play, Minecraft Season Pass)
- Aplicação de cupons e cálculo do valor total

---

## 📁 Dados Utilizados

### Estrutura da Base de Dados (`Bases`)

Contém os registros detalhados de cada cliente e suas escolhas de plano. As principais colunas incluem:

- `Plan`, `Subscription Type`, `Start Date`, `Auto Renewal`
- `Subscription Price`, `EA Play Season Pass`, `Minecraft Season Pass`
- `Coupon Value`, `Total Value`

---

## 🔄 Tabelas Dinâmicas

As análises realizadas com Tabelas Dinâmicas respondem a perguntas de negócio:

### 1. Faturamento Total de Planos Anuais
- **Filtro**: `Subscription Type` = Annual
- **Campo de linha**: `Auto Renewal`
- **Campo de valor**: Soma de `Total Value`

### 2. Comparativo de Faturamento com e sem Renovação
- **Mesma estrutura acima**, mantendo filtro em planos anuais

### 3. Vendas de EA Play Season Pass
- **Filtro**: `Subscription Type` = Quarterly
- **Campo de linha**: `Plan`
- **Campo de valor**: Soma de `EA Play Season Pass`

### 4. Vendas de Minecraft Season Pass
- **Filtro**: `Subscription Type` = Quarterly
- **Campo de linha**: `Plan`
- **Campo de valor**: Soma de `Minecraft Season Pass Price`

---

## 🧠 Fórmulas Utilizadas

Além das Tabelas Dinâmicas, foram aplicadas fórmulas simples e condicionais como:

- **Cálculo do valor total da assinatura**:
  ```excel
  =SOMA([@Subscription Price]; [@EA Play Season Pass Price]; [@Minecraft Season Pass Price]) - [@Coupon Value]
