# Mapeando a Desigualdade Urbana com Python

Análise de vulnerabilidade socioambiental em Belo Horizonte com dados do Censo 2022, utilizando Python e geoprocessamento.

🔗 **[Acessar o repositório](https://github.com/larissacodes/indicador-vulnerabilidade-bh)**

---

## Sobre o projeto

Este projeto constrói um índice de vulnerabilidade socioambiental para os setores censitários de Belo Horizonte a partir de dados do Censo Demográfico 2022 do IBGE.

A análise parte de um problema central: **dados agregados escondem desigualdades intraurbanas**. Ao trabalhar na escala de setor censitário (5.166 unidades em Belo Horizonte), é possível revelar padrões territoriais invisíveis em médias municipais.

O projeto é totalmente replicável para qualquer município brasileiro.

---

## O que é construído

- Índice de vulnerabilidade socioambiental por setor censitário
- Mapas temáticos com classificação em quintis
- Análise territorial da desigualdade urbana

---

## Indicadores utilizados

O índice é composto por quatro indicadores (todos em proporção):

- Percentual de domicílios sem rede geral de água  
- Percentual de domicílios sem rede de esgoto  
- Percentual de domicílios sem coleta de lixo  
- Percentual de domicílios sem banheiro  

O índice final é a média simples dos quatro:
Vulnerabilidade = (Água + Esgoto + Lixo + Banheiro) / 4


- Valor 0 → nenhuma vulnerabilidade  
- Valor 1 → vulnerabilidade máxima  

---

## Dados

Todos os dados são públicos:

- Malha de setores censitários — IBGE (Censo 2022)  
- Agregados por setor censitário — IBGE (domicílios)  
- Dicionário de dados — IBGE  

---

## Metodologia

O fluxo analítico inclui:

1. **Carregamento e filtragem geográfica**
   - Seleção dos setores de Belo Horizonte

2. **Tratamento de dados**
   - Limpeza de inconsistências (aspas, colunas duplicadas)
   - Padronização de identificadores

3. **Construção dos indicadores**
   - Cálculo de proporções por setor

4. **Criação do índice**
   - Média simples dos quatro indicadores

5. **Integração espacial**
   - Merge entre dados tabulares e geometria

6. **Visualização**
   - Mapas coropléticos com classificação em quintis

---

## Principais resultados

- Forte padrão de desigualdade centro-periferia  
- Concentração de vulnerabilidade nas bordas da cidade  
- Grande dispersão entre setores (diferenças superiores a 100x)  
- Esgotamento sanitário como principal gargalo  
- Abastecimento de água relativamente universalizado  

---

## Limitações

- Dados preliminares do Censo 2022  
- Ausência de renda por setor censitário  
- Índice com pesos iguais (não ponderado)  

---

## Próximos passos

- Inclusão de renda (quando disponível)  
- Integração com dados ambientais (CPRM, MapBiomas)  
- Aplicação de PCA ou ponderações teóricas  
- Expansão para outros municípios  

---

## 🗂️ Estrutura do repositório
```
vulnerabilidade-bh
├── CITATION.cff    # metadados para citação acadêmica
├── LICENSE         # licença CC BY-NC 4.0
├── README.md       # documentação do projeto
└── analise.ipynb   # notebook com todo o processo analítico
```

---

## Autoria

**Larissa Diniz Aguiar**  
Professora Assistente - Departamento de Relações Internacionais, PUC Minas  
Mestre em Ciência Política (UFMG)
Analista de Dados - Laboratório de Pesquisa e Projetos em Relações Internacionais 

- LinkedIn: https://www.linkedin.com/in/larissadinizaguiar  
- Lattes: http://lattes.cnpq.br/9454344975691413  

---

## Licença

Este projeto está licenciado sob Creative Commons Atribuição-NãoComercial 4.0 Internacional (CC BY-NC 4.0).

---

## Como replicar

1. Baixe os dados do IBGE (Censo 2022)
2. Ajuste o código do município desejado
3. Execute o notebook

---

## Referência sugerida

Se utilizar este projeto, cite conforme indicado no arquivo `CITATION.cff`.
