# <img src="https://www.r-project.org/logo/Rlogo.png" width="30" height="30"> Portfólio de Análise de Dados com R

[![R Version](https://img.shields.io/badge/R-4.3.2+-276DC3?logo=r&logoColor=white)](https://www.r-project.org/)
[![RStudio](https://img.shields.io/badge/RStudio-2023.12+-75AADB?logo=rstudio)](https://www.rstudio.com/)
[![Licença](https://img.shields.io/badge/Licença-MIT-green)](LICENSE)

Repositório profissional demonstrando aplicações avançadas da linguagem R em análise de dados, estatística e visualização.
# Conceitos Básicos de R

Este repositório reúne **três scripts introdutórios** em R, com foco em conceitos fundamentais da linguagem.

## Arquivos

### `operadores_matematicos.R`

Demonstra o uso dos principais operadores matemáticos em R:

- Operações básicas: soma, subtração, multiplicação e divisão  
- Potenciação e radiciação  
- Módulo e fatorial  
- Logaritmos e exponenciais  
- Funções trigonométricas (em radianos)  
- Notação científica  
- Constante `pi` e consulta da versão do R  

### `variaveis.R`

Apresenta a criação e manipulação de objetos (variáveis) em R:

- Atribuição de valores  
- Boas práticas de nomenclatura  
- Tipos básicos de dados: `numeric`, `integer`, `complex`, `character`, `logical` e `factor`  
- Conversão entre tipos  
- Uso da função `length()` para verificar o comprimento de objetos  

### `fatores.R`

Explora o uso de fatores (factors), uma estrutura de dados utilizada para representar variáveis categóricas:

- Criação de fatores a partir de vetores com valores categóricos  
- Comparação entre vetores comuns e fatores  
- Uso das funções `summary()` e `table()` para análise de frequência  
- Aplicação prática: categorias como nível de escolaridade e tensão elétrica residencial (110V, 220V)  

### `matriz.R`

Apresenta a criação e manipulação de **matrizes**, estruturas bidimensionais organizadas em linhas e colunas:

- Criação de matrizes com números e com caracteres  
- Acesso a elementos por índice  
- Combinação de vetores com `rbind()`  
- Nomeação de linhas e colunas com `dimnames`  
- Operações com matrizes: soma, subtração, multiplicação escalar e matricial  
- Cálculo de média e soma por linha e por coluna com `rowMeans()`, `colMeans()`, `rowSums()` e `colSums()`  
## 🧩 Técnicas Demonstradas

### 🔧 Manipulação de Dados
```r
# Limpeza e transformação com tidyverse
library(tidyverse)

dados <- read_csv("dados.csv") %>%
  filter(!is.na(valor)) %>%
  mutate(
    valor_ajustado = log(valor),
    categoria = factor(categoria, levels = c("Baixo", "Médio", "Alto"))
  ) %>%
  group_by(regiao) %>%
  summarise(media = mean(valor_ajustado, na.rm = TRUE))
```
### 📊 Visualização Avançada
```r
# Gráficos interativos com ggplot2 + plotly
library(ggplot2)
library(plotly)

grafico <- ggplot(dados, aes(x = idade, y = renda, color = educacao)) +
  geom_point(alpha = 0.7) +
  geom_smooth(method = "lm") +
  labs(title = "Renda por Idade e Educação",
       x = "Idade (anos)",
       y = "Renda (R$)") +
  theme_minimal()

ggplotly(grafico)
```
### 📈 Modelagem Estatística
```r
# Análise de regressão linear múltipla
modelo <- lm(renda ~ idade + educacao + experiencia, data = dados)

# Diagnóstico do modelo
library(broom)
tidy(modelo) %>%
  kable(digits = 3, caption = "Resultados da Regressão")

glance(modelo) %>%
  kable(caption = "Métricas do Modelo")
```
```
portfolio-R/
├── Introdução/
├── Linguagem R/
```

### 🛠️ Stack Completa
| Categoria      | Pacotes/Ferramentas                     |
|----------------|------------------------------------------|
| Manipulação    | dplyr, tidyr, readr, purrr              |
| Visualização   | ggplot2, plotly, ggthemes               |
| Modelagem      | caret, lm, glmnet, randomForest         |
| Relatórios     | RMarkdown, bookdown, knitr              |
| Interatividade | shiny, flexdashboard                    |

## 📬 Contato e Redes

-[LinkedIn](https://www.linkedin.com/in/daniel-mendes-a64326140)



