# Telecom Churn - Limpeza e Tratamento de Dados

Este projeto foi desenvolvido com o objetivo de construir um pipeline de ETL (Extração, Transformação e Carga) para tratar uma base de dados de clientes de uma empresa de telecomunicações. Os dados originais apresentavam estruturas aninhadas em formato JSON, dados ausentes e inconsistências de tipo que foram completamente tratadas utilizando Python e Pandas.

## 🛠️ Tecnologias e Bibliotecas Utilizadas
* **Python 3**
* **Pandas**: Manipulação, limpeza e normalização dos dados.
* **Google Colab**: Ambiente de desenvolvimento em nuvem.

## 📈 Etapas do Pipeline de Dados (O que foi feito)
* **Normalização de JSON:** Desaninhamento de dicionários complexos (`cliente`, `telefone`, `internet`, `conta`) para o formato de colunas tabulares com `pd.json_normalize`.
* **Tratamento de Strings Vazias e Nulos:** Identificação e conversão de valores vazios (como o objeto `None`) que corrompiam o tipo das colunas.
* **Conversão de Tipos de Dados:** Uso de `.astype()` e `pd.to_numeric()` para transformar colunas tratadas como texto (`object`) em tipos numéricos adequados (`int` e `float`).
* **Correção de Outliers com Seleção Avançada:** Aplicação de máscaras booleanas combinadas com o operador `.loc` para corrigir distorções em registros de tempo de serviço.
* **Otimização do DataFrame:** Ajuste de índices com `.reset_index(drop=True)` para manter a integridade da tabela após as remoções.
* * **Remoção de Dados Duplicados:** Identificação e eliminação de registros repetidos (linhas duplicadas) utilizando os métodos `.duplicated()` e `.drop_duplicates()`, garantindo a unicidade e a integridade de cada registro na base de dados.
  * * **Limpeza de Strings com Expressões Regulares (Regex):** Uso do método `.str.replace()` combinado com Regex para identificar, limpar e remover caracteres não numéricos (como símbolos, espaços ocultos ou letras) em colunas que deveriam ser estritamente numéricas, permitindo a conversão correta dos tipos.
