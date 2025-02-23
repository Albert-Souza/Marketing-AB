# Marketing-AB

Testes A/B de uma campanha de marketing

## Dataset
https://www.kaggle.com/datasets/faviovaz/marketing-ab-testing

### Informações sobre os dados  

- **test group**: Se for `"ad"`, a pessoa viu o anúncio; se for `"psa"`, ela viu apenas o anúncio de utilidade pública.  
- **converted**: Se a pessoa comprou o produto, então `True`; caso contrário, `False`.  
- **total ads**: Quantidade de anúncios vistos pela pessoa.  
- **most ads day**: Dia em que a pessoa viu a maior quantidade de anúncios.  
- **most ads hour**: Hora do dia em que a pessoa viu a maior quantidade de anúncios.

## Análise

### Teste A/B: "Grupos de teste" e "Conversões"

Há alguma diferença na taxa de conversão entre os grupos AD e PSA?

**Hipótese Nula**: Não há diferença significativa entre as taxas de conversão dos grupos (P(ad) - P(psa) = 0)  
**Hipótese Alternativa**: Há diferença significativa entre as taxas de conversão (P(ad) - P(psa) ≠ 0)  
**Nível de Significância**: 0.05

### Conclusões do Teste A/B: "Grupos de teste" e "Conversões"

Taxa de conversão do grupo AD: 2.55%  
Taxa de conversão do grupo PSA: 1.79%  

Utilizando o **Teste Z**, obtivemos um **p-valor < 0.0001**, permitindo rejeitar a hipótese nula. O intervalo de confiança de 95% para a diferença entre as taxas de conversão foi de **(0.60%, 0.94%)**.

Em termos percentuais, o grupo AD apresentou um aumento na conversão entre **33.33%** e **52.84%** em relação ao grupo PSA, evidenciando uma vantagem significativa.

Os dados demonstram que a estratégia aplicada no grupo AD gerou uma taxa de conversão significativamente maior que a do grupo PSA. Esses resultados indicam que a abordagem adotada no grupo AD teve um impacto positivo e relevante, validando a eficácia da campanha.

### Análise: "Anúncios Totais" e "Conversão"

Qual o impacto da quantidade de anúncios vistos pelas pessoas na taxa de conversão?

### Gráficos de distribuição

![Anúncios vistos - Violinplot](https://github.com/Albert-Souza/Marketing-AB/blob/main/visualizations/ads_seen_violinplot.png?raw=true)

![Anúncios vistos - Histograma](https://github.com/Albert-Souza/Marketing-AB/blob/main/visualizations/ads_seen_histogram.png?raw=true)

### Conclusões da Análise: "Anúncios Totais" e "Conversão"

Os usuários foram categorizados em sete faixas de exposição, baseadas no número total de anúncios vistos:


- **very-low**: entre 0 e 20 anúncios vistos
- **low**: entre 20 e 40 anúncios vistos
- **medium-low**: entre 40 e 60 anúncios vistos
- **medium**: entre 60 e 80 anúncios vistos
- **medium-high**: entre 80 e 100 anúncios vistos
- **high**: entre 100 e 120 anúncios vistos
- **very-high**: entre 120 e 140 anúncios vistos

#### Resultados

A taxa de conversão observada em cada faixa foi:

- **very-low**:	0.50%
- **low**:	2.31%
- **medium_low**:	6.60%
- **medium**:	11.77%
- **medium_high**:	15.45%
- **high**:	17.42%
- **very-high**:	18.36%

Comparação com a classe anterior:

- **low** possui 364.93% mais conversões que **very-low**
- **medium_low** possui 185.73% mais conversões que **low**
- **medium possui** 78.35% mais conversões que **medium_low**
- **medium_high** possui 31.29% mais conversões que **medium**
- **high** possui 12.76% mais conversões que **medium_high**
- **very-high** possui 5.43% mais conversões que **high**

Os dados sugerem que a exposição a anúncios tem um impacto positivo na conversão até certo ponto. No entanto, o crescimento percentual diminui à medida que a quantidade de anúncios aumenta, sugerindo um possível efeito de saturação. Isso indica que **exibir mais de 140 anúncios pode ser contraproducente**.

Estratégias de exposição devem focar em levar usuários até a faixa **medium-high (80-100 anúncios)**, pois depois disso o ganho marginal é pequeno.

### Teste A/B/n: "Dias com mais anúncios" e "Conversões"
Existe diferença significativa nas conversões dependendo do dia da semana que cada indivíduo mais viu anúncios?  
Se sim, quais dias foram mais importantes?

### Conclusões do Teste A/B/n: "Dias com mais anúncios" e "Conversões"

Para essa análise foi utilizado o **Teste Qui-Quadrado** com **Nível de Significância = 0.05**

Utilizando o Teste Qui-Quadrado, obtivemos um **p-valor < 0.0001**, indicando que há uma diferença estatística significativa entre os dias.

A taxa de conversão observada baseado no dia em que mais anúncios foram vistos foi:

- **Segunda**:	3.28%
- **Terça**:	2.98%
- **Quarta**:	2.49%
- **Quinta**:	2.16%
- **Sexta**:	2.22%
- **Sábado**:	2.11%
- **Domingo**:	2.45%

Comparações relevantes:

- **Segunda** possui 9.96% mais conversões que **Terça**
- **Segunda** possui 31.55% mais conversões que **Quarta**
- **Segunda** possui 52.11% mais conversões que **Quinta**
- **Segunda** possui 47.72% mais conversões que **Sexta**
- **Segunda** possui 55.87% mais conversões que **Sábado**
- **Segunda** possui 34.06% mais conversões que **Domingo**


- **Terça** possui 19.64% mais conversões que **Quarta**
- **Terça** possui 38.34% mais conversões que **Quinta**
- **Terça** possui 34.34% mais conversões que **Sexta**
- **Terça** possui 41.75% mais conversões que **Sábado**
- **Terça** possui 21.92% mais conversões que **Domingo**


- **Quarta** possui 15.63% mais conversões que **Quinta**
- **Quarta** possui 12.29% mais conversões que **Sexta**
- **Quarta** possui 18.48% mais conversões que **Sábado**
- **Quarta** possui 1.91% mais conversões que **Domingo**


- **Domingo** possui 13.47% mais conversões que **Quinta**
- **Domingo** possui 10.19% mais conversões que **Sexta**
- **Domingo** possui 16.27% mais conversões que **Sábado**

Os dados indicam que os dias iniciais da semana (segunda e terça) apresentam as taxas de conversão mais altas, seguidos por quarta e domingo. Portanto, para maximizar o retorno das campanhas publicitárias, recomenda-se concentrar esforços nesses dias, especialmente na segunda-feira, que obteve o desempenho superior.

### Teste A/B/n: "Horário com mais anúncios" e "Conversões"
Existe diferença significativa nas conversões dependendo horário que cada indivíduo mais viu anúncios?  
Se sim, quais horários foram mais importantes?

### Conclusões do Teste A/B/n: "Horário com mais anúncios" e "Conversões"

Para essa análise foi utilizado o **Teste Qui-Quadrado** com **Nível de Significância = 0.05**

Utilizando o Teste Qui-Quadrado, obtivemos um **p-valor < 0.0001**, indicando que há uma diferença estatística significativa entre o horário.

A taxa de conversão observada baseado no horário em que mais anúncios pode ser visualizada no seguinte gráfico:

![Conversão por horário](https://github.com/Albert-Souza/Marketing-AB/blob/main/visualizations/conversion_by_hour.png?raw=true)

É possível notar um comportamento senoidal na taxa de conversão. Durante o período entre 00:00 e 09:00 horas, a conversão é significativamente menor. Por outro lado, a janela entre 14:00 e 21:00 horas revela-se mais propícia para conversões, sugerindo que a alocação de anúncios nesse período pode maximizar os resultados das campanhas.

O pior horário para conversão é 02:00hrs enquanto o melhor é 16:00hrs.

## Conclusões Gerais

### Grupos AD vs. PSA
A abordagem aplicada no grupo AD demonstrou um impacto positivo e relevante na taxa de conversão, com uma taxa de conversão entre 33.33% e 52.84% maior em relação ao grupo PSA.

### Quantidade de Anúncio
A exposição a anúncios tem efeito positivo na conversão, mas com ganhos marginais decrescentes após a faixa de 80-100 anúncios. Estratégias que ultrapassem essa faixa podem levar à saturação do usuário.

### Dias da Semana
Segunda e terça, são os mais promissores para conversões, justificando uma estratégia focada nesses períodos.

### Horários
A alocação de anúncios entre 14:00 e 21:00 horas é ideal, com o melhor desempenho às 16:00 hrs, enquanto horários muito cedo ou muito tarde apresentam desempenho inferior.
