# SISTEMA DE GESTÃO DE VENDAS COM BANCO RELACIONAL E DATA WAREHOUSE

*Trabalho Final da disciplina de Banco de Dados do Bacharelado em Inteligência Artificial UFG | 2024-1*

- Jair Martins Santiago Neto - 202300619
- Lídia Rakel Alcântara do Vale - 202305743

---

Neste trabalho, desenvolvemos um sistema de gestão de vendas de uma rede de lojas de produtos agrícolas utilizando Banco de Dados Relacional e Data Warehouse como trabalho final da disciplina de Banco de Dados do Bacharelado em Inteligência Artificial da UFG. Ao final, foi montado um dashboard em Power BI para visualização das análises.

A apresentação do trabalho está disponível [aqui](https://www.canva.com/design/DAGL_MguhGY/uhfWLNdHDMT2h4XJlYFh2Q/edit?utm_content=DAGL_MguhGY&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton).

---

## Banco Realcional

### Modelagem

A modelagem do banco relacional foi feita considerando 5 tabelas: Lojas, Categorias, Clientes, Produtos e Saídas (vendas). Os dados foram fornecidos anonimizados, sem identificar pessoas ou lojas por informações sensíveis, como nome, CPF, CNPJ, etc.

![MER-Vendas-Agro](https://github.com/user-attachments/assets/9fd3fb51-ad0b-4aec-87b4-3a6d7c8eb5b2)

### Implementação

A implementação foi feita no Google Cloud Platform pelo CloudSQL. Ó código-fonte da implementação está disponível [aqui](https://github.com/lidiavale/TrabalhoFinalBD/blob/94d944a7e144e119acae6f751ceb6b14c38ca1e5/ImplementacaoBDR.sql), em linguagem SQL.

A inclusão de dados nas tabelas foi feita pela importação de arquivos CSV alocados em um bucket na GCP.

---

## Data Warehouse

### Modelagem

A modelagem do data warehoudr foi feita considerando uma tabela de Fato (Saídas/vendas) e 5 tabelas de dimenões (Lojas, Categorias, Clientes, Produtos e Datas). Os dados foram fornecidos anonimizados, sem identificar pessoas ou lojas por informações sensíveis, como nome, CPF, CNPJ, etc.

![Modelagem Data Warehouse](https://github.com/user-attachments/assets/2068880b-9098-4329-a1f2-3ff45ebda299)

### Implementação

A implementação foi feita no Google Cloud Platform pelo BigQuery, seguindo o processo ETL.

![ETL](https://github.com/user-attachments/assets/a8d4c9f7-3d6f-4aa3-b03c-84e4135364bd)

As tabelas foram criadas e populadas a partir da conexão externa entre o BigQuery e o CloudSQL. A transformação dos dados foi feita pela conversão dos formatos de datas para ano, mês e dia e também pelo tratamento de campos NULL com a inclusão de "dado não existente".

---

## Ferramenta de BI

Foi montando um dashboard no Power BI contendo visuais de:
- Faturamento
- Ticket Médio
- Margem
- Distribuição espacial dos clientes
- Evolução temporal das vendas
- Ranqueamento em R$ de regional, filial e vendedor
- Mix de categorias de venda

Foram incluídos filtros para apoiar as análises, sendo eles:
- Data do faturamento
- Regional e filial
- Vendedor (por código)
- Categoria
- Produto

![Painel_2](https://github.com/user-attachments/assets/72ad7949-cec7-4451-8be1-aedb478df57e)


---

Feito por [Jair Martins](jairneto@discente.ufg.br) e [Lídia do Vale](lidia.vale@discente.ufg.br)
