# Competitividade do Etanol vs. Gasolina e Consumo de Etanol no Brasil

Projeto acadêmico desenvolvido na disciplina de **Métodos Computacionais para Economia** — FEA-USP.

## Contexto

Veículos flex fuel permitem substituição entre gasolina e etanol. Pela "regra dos 70%", o etanol tende a ser vantajoso para o consumidor quando seu preço custa menos de 70% do preço da gasolina.

**Pergunta de pesquisa:** períodos de maior competitividade de preço do etanol coincidem com maior consumo?

## Hipótese

Quanto menor o preço relativo do etanol (preço do etanol / preço da gasolina), maior o seu consumo.

## Dados

Bases públicas da **ANP (Agência Nacional do Petróleo, Gás Natural e Biocombustíveis)**:
- Preços semanais/mensais de gasolina comum e etanol hidratado (2018–2026)
- Volumes de vendas mensais de etanol hidratado e gasolina C, agregados nacionalmente

## Metodologia

1. Coleta automatizada dos dados via requisições HTTP às bases abertas da ANP
2. Limpeza e padronização (conversão de formatos de data e valores numéricos, tratamento de mudanças no formato dos arquivos da ANP ao longo dos anos)
3. Agregação mensal de preços e vendas, e integração das duas bases
4. Construção de variáveis: preço relativo, consumo de etanol, indicador de competitividade (limiar de 0,70)
5. Análise estatística:
   - Comparação de médias entre períodos competitivos e não competitivos
   - Teste t de Student para diferença de médias
   - Correlação de Pearson e Spearman entre preço relativo e consumo
   - Regressão linear simples

## Principais resultados

- Consumo médio de etanol foi cerca de **16,6% maior** em períodos competitivos (preço relativo < 0,70)
- Teste t confirmou diferença estatisticamente significativa entre os grupos (**t = 4,21, p < 0,001**)
- Correlações de Pearson e Spearman indicaram relação **negativa moderadamente forte** entre preço relativo e consumo (p < 0,001)

## Conclusão

Os resultados são consistentes com a teoria da demanda para bens substitutos: maior competitividade de preço do etanol está associada a maior consumo, sugerindo que o preço relativo é um determinante relevante da demanda por etanol no Brasil.

**Limitações:** análise descritiva, sem inferência causal; não controla por variáveis como renda, atividade econômica, tributação e fatores regionais — próximos passos incluiriam modelos econométricos com esses controles.

## Ferramentas utilizadas

`Python` · `pandas` · `matplotlib` · `scipy.stats` (testes de hipótese, correlação e regressão)

## Autoria

Projeto desenvolvido em grupo, como parte da disciplina de Métodos Computacionais para Economia (EAE1106 — FEA-USP):

- **Pedro** e **Enzo** — construção das bases de dados
- **Miguel** e **Cairo** — construção da análise
- **Carlos** — elaboração do relatório final

Contribuição individual (Cairo): construção da análise estatística (teste t, correlações de Pearson e Spearman, regressão linear e interpretação dos resultados).

