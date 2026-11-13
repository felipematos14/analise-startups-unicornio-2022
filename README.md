# 🦄 Análise de Startups Unicórnio (até setembro de 2022)

Análise exploratória em Python de uma base com **1.186 startups unicórnio** — empresas de capital fechado avaliadas em mais de **US$ 1 bilhão**. O objetivo é entender **onde** essas empresas nascem, **em quais setores** concentram mais valor e **como** o número de novos unicórnios evoluiu ao longo dos anos.

## 📂 Conteúdo do repositório

| Arquivo | Descrição |
|---|---|
| `Projeto_Unicórnio.ipynb` | Notebook com todo o código da análise |
| `unicorns_till_sep_2022.csv` | Base de dados utilizada |

**Fonte dos dados:** [Unicorn Startups – Kaggle](https://www.kaggle.com/ramjasmaurya/unicorn-startups)

## 🗂️ Sobre a base de dados

| Coluna original | Descrição |
|---|---|
| `Company` | Nome da empresa |
| `Valuation ($B)` | Valor de mercado, em bilhões de dólares |
| `Date Joined` | Data em que a empresa atingiu o status de unicórnio |
| `Country` | País sede |
| `City` | Cidade sede |
| `Industry` | Setor de atuação |
| `Investors` | Principais investidores |

Dimensão: **1.186 linhas × 7 colunas**.

## 🛠️ Tecnologias

- Python 3
- Pandas e NumPy (manipulação dos dados)
- Matplotlib e Seaborn (visualizações)
- Jupyter Notebook / Google Colab

## ⚙️ O que o código faz

1. **Importa as bibliotecas** e **carrega o CSV** em um DataFrame do Pandas.
2. **Inspeciona a base**: dimensões (`shape`), tipos de dados (`info`) e primeiras linhas (`head`).
3. **Renomeia as colunas** para português (`Empresa`, `Valor ($)`, `Data de Adesão`, `Pais`, `Setor` etc.).
4. **Analisa valores nulos**: conta os campos vazios por coluna e os exibe em um *heatmap*. Apenas a coluna de investidores tem nulos (18 registros).
5. **Conta empresas por setor** (`value_counts`) para ver quais áreas têm mais unicórnios.
6. **Ranking de países**: conta unicórnios por país e plota um gráfico de barras com o **Top 10**.
7. **Trata a coluna de valor**: remove o símbolo `$` e converte o texto em número (`float`), permitindo cálculos.
8. **Soma o valor por setor** (`groupby` + `sum`) e plota os **5 setores com maior valor acumulado**.
9. **Trata a coluna de data**: converte `Data de Adesão` para o tipo `datetime` e extrai o **ano** em uma nova coluna.
10. **Conta quantas empresas viraram unicórnio em cada ano** e plota um **gráfico de linha** com a evolução temporal.

## 📊 O que é possível extrair dos resultados

### 1. Onde estão os unicórnios (Top 10 países)

| País | Unicórnios |
|---|---|
| 🇺🇸 Estados Unidos | 636 |
| 🇨🇳 China | 174 |
| 🇮🇳 Índia | 70 |
| 🇬🇧 Reino Unido | 46 |
| 🇩🇪 Alemanha | 29 |
| 🇫🇷 França | 24 |
| 🇮🇱 Israel | 22 |
| 🇨🇦 Canadá | 19 |
| 🇧🇷 Brasil | 17 |
| 🇰🇷 Coreia do Sul | 17 |

- Os **EUA concentram mais da metade** (~54%) dos unicórnios da base, e juntos com a China passam de 68%.
- A **Índia** aparece em terceiro lugar, à frente de toda a Europa.
- O **Brasil** está entre os 10 maiores, com 17 empresas.

### 2. Quais setores concentram mais valor

| Setor | Valor acumulado (US$ bilhões) | Nº de empresas |
|---|---|---|
| Fintech | 855,43 | 239 |
| Internet software & services | 660,93 | 224 |
| E-commerce & direct-to-consumer | 387,19 | 103 |
| Artificial intelligence | 315,01 | 74 |
| Other | 293,72 | 65 |

- **Fintech** lidera tanto em quantidade de empresas quanto em valor acumulado.
- Fintech e software/internet juntos somam mais de **US$ 1,5 trilhão** em valor de mercado.
- Inteligência artificial tem relativamente poucas empresas (74), mas um valor acumulado alto, indicando **valuations médios elevados** no setor.

### 3. Evolução ao longo do tempo

| Ano | Novos unicórnios |
|---|---|
| 2007 – 2014 | 1 a 12 por ano |
| 2015 | 34 |
| 2016 | 21 |
| 2017 | 44 |
| 2018 | 98 |
| 2019 | 102 |
| 2020 | 108 |
| **2021** | **529** |
| 2022 (até set.) | 228 |

- Até 2017 o fenômeno era raro; a partir de 2018 o ritmo passou de ~100 novos unicórnios por ano.
- **2021 foi um ano excepcional**: 529 novas empresas, quase 5× o ano anterior.
- Só em 2021 e 2022 (até setembro) surgiram **cerca de 64%** de todos os unicórnios da base.

## ⚠️ Limitações e observações sobre os dados

- Algumas linhas da base original têm colunas deslocadas (investidores aparecendo na coluna `Setor`), o que gera categorias de setor inválidas.
- Há duas grafias para o mesmo setor: `Artificial intelligence` e `Artificial Intelligence`.
- O valor é a avaliação de mercado **no momento da base** (set/2022), não reflete mudanças posteriores.
- A análise mostra **quantidade e valor acumulado**, não rentabilidade ou desempenho das empresas.

## 🚀 Como executar

1. Clone o repositório:
   ```bash
   git clone <url-do-seu-repositorio>
   ```
2. Instale as dependências:
   ```bash
   pip install numpy pandas matplotlib seaborn jupyter
   ```
3. Abra o notebook e ajuste o caminho do CSV na leitura dos dados:
   ```python
   Base_Dados = pd.read_csv('unicorns_till_sep_2022.csv')
   ```
4. Execute as células em ordem.

## 🔮 Próximos passos

- Limpar as linhas com colunas deslocadas e unificar categorias de setor.
- Analisar os investidores que mais aparecem entre os unicórnios.
- Comparar valor acumulado por país, e não apenas a quantidade.
- Analisar os unicórnios brasileiros em detalhe.

## 👤 Autor

**Felipe Matos Pessoa dos Santos** — [LinkedIn](https://linkedin.com/in/felipe-matospessoa) · [GitHub](https://github.com/felipematos14)
