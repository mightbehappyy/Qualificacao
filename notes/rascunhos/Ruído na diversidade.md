# Ruído na diversidade ideal: a proposta cai por terra?

Ruído na relação de diversidade não derruba a proposta por si só: o que decide é onde está o ruído e quanto sinal sobra por baixo dele. Só um cenário a derrubaria de fato, descrito a seguir, e mesmo ele muda a forma do trabalho em vez de acabar com ele.

## O que realmente derrubaria a proposta

O único cenário fatal é a ausência de qualquer estrutura temporal explorável na diversidade ideal (D*) ou na sua relação com o erro, depois de bem testada: nada que supere a persistência ou a média histórica. Ruído alto, isolado, não prova isso.

## Por que ruído não é ausência de estrutura

Quatro situações em que o ruído esconde o sinal em vez de eliminá-lo:

- **Ruído de estimação:** calcular D* em janelas curtas gera valores instáveis só por amostragem. Janelas maiores, suavização (média móvel exponencial) ou métricas mais robustas podem revelar a estrutura.
- **Sinal em outra escala:** o valor ponto a ponto pode ser imprevisível, mas o nível, a tendência ou a mudança de regime pode ser previsível. Dá para prever uma faixa (baixa, média, alta) em vez do valor exato.
- **Sinal condicional:** a relação pode ser fraca no geral e forte em certos regimes, como alta volatilidade ou pós-drift. Esta é a hipótese H2.
- **Heterogeneidade entre séries:** pode haver estrutura em parte das séries e não em outras. Caracterizar quais (sazonalidade, tamanho, ruído) já é um resultado.

## Protocolo de testes para separar ruído de estrutura

O protocolo tem cinco passos, cada um com um critério de decisão fixado antes de ver os resultados. Limiares e tamanhos abaixo são valores iniciais sugeridos, não obrigatórios.

**Configuração fixa**

1. **Dados:** subconjunto do M4 por frequência e do Monash Forecasting Repository, estratificado por sazonalidade, tendência e tamanho da série.
2. **Pool:** 8 a 12 modelos heterogêneos, como ETS, ARIMA, Theta, um modelo de árvores e uma rede (MLP ou N-BEATS).
3. **Validação:** rolling origin. Em cada origem t, tudo é calculado apenas com dados até t.
4. **Diversidade:** três métricas (variância entre previsões, correlação dos erros, ambiguidade de Krogh e Vedelsby) em janelas de tamanho w, com três valores de w.
5. _D (oráculo):_* em cada janela, a diversidade do subconjunto que teria minimizado o erro do ensemble. É definida ex post e nunca entra como insumo de decisão.

|   |   |   |   |
|---|---|---|---|
|Passo|Pergunta|Teste ou métrica|Critério de decisão|
|1. Estrutura|QP1|ACF/PACF e Ljung-Box em D*; ADF e KPSS; expoente de Hurst; comparação com séries embaralhadas por blocos (permutação)|Há estrutura se o valor observado fica fora do intervalo de 95% das permutações em parcela relevante das séries|
|2. Sensibilidade|QP1|Repetir o passo 1 com 3 janelas, 3 métricas e 2 tamanhos de pool|Conclusão estável entre as combinações, ou instabilidade relatada|
|3. Previsibilidade|QP2|AR(p) e regressão com lags e variáveis de regime para prever D*; contra persistência, média móvel de k janelas e média histórica; MAE, RMSE e Diebold-Mariano|Supera todas as referências com p < 0,05 após correção de Holm|
|4. Relação com o erro|QP3|Distância entre a diversidade atual e D* contra o excesso de erro do ensemble; correlação cruzada com lags e Granger; separação por regime (volatilidade em tercis, janelas pós-drift)|Relação significativa e de sinal consistente em ao menos um regime|
|5. Aplicação|QP4|Seleção guiada por D* estimado contra média simples, DETS, ADE e DEMSC; MASE e sMAPE; Diebold-Mariano, Model Confidence Set e diagrama de diferença crítica|Melhora significativa sobre a melhor referência, ou relato dos estratos em que ela ocorre|

**Regras do protocolo**

- Nenhum cálculo usa informação posterior à origem t (sem vazamento temporal).
- Corrigir comparações múltiplas (Holm) e repetir com várias sementes nos modelos estocásticos.
- Relatar os resultados por estrato de série, não só a média geral.

## Se o resultado for negativo

Um resultado negativo muda a contribuição, não a invalida. Se os passos 1 ou 3 falharem, o trabalho passa a mostrar quando e por que a diversidade não é explorável de forma antecipativa, o que evita esforço mal direcionado em outros estudos.

- A seleção pode seguir reativa, mas informada pela relação entre diversidade e erro por regime (passo 4), sem precisar prever.
- A hipótese H3 seria reescrita: comparar a seleção por desempenho recente contra a seleção por desempenho mais diversidade condicionada ao regime.

## Implicação para as perguntas de pesquisa

QP1 e QP2 devem ser formuladas como perguntas abertas, e não como confirmações esperadas. Admitir de antemão a possibilidade de resultado negativo, com critérios definidos antes dos experimentos, torna o trabalho mais defensável perante revisores.