---
autores: Danny Wood, Tingting Mu, Andrew M Webb, Henry W J Reeve, Mikel Lujan, Gavin Brown
ano: "2023"
titulo: A Uniﬁed Theory of Diversity in Ensemble Learning
chave_citacao: "@woodUnifiedTheoryDiversity"
tags:
  - fichamento
  - ensemble
  - diversidade
  - series-temporais
status: lido
---

# A Uniﬁed Theory of Diversity in Ensemble Learning (2023)
- **Zotero:** [Abrir PDF no Zotero]([Wood et al. - A Uniﬁed Theory of Diversity in Ensemble Learning.pdf](zotero://select/library/items/ZGDT767X))

## Síntese em 3 linhas
*(Preencher após importar)*

---

## 1. Definições e Conceitos (🟡)
> [!warning] Definição (p. 1)
> "Our framework reveals that diversity is in fact a hidden dimension in the bias-variance decomposition of the ensemble loss." [Ver no PDF](zotero://open-pdf/library/items/ZGDT767X?page=1&annotation=AZWIF75N)
> **Minha nota:** Classica definição dada por esse estudo

> [!warning] Definição (p. 1)
> "diversity is a measure of model fit, in precisely the same sense as bias and variance, but accounting for statistical dependencies between ensemble members" [Ver no PDF](zotero://open-pdf/library/items/ZGDT767X?page=1&annotation=7NZZUZSV)
> **Minha nota:** Diversidade é uma métrica do ajuste do modelo da mesma forma que viés e variancia, mas contando com a dependencia estatistica entre os membros do ensemble

> [!warning] Definição (p. 2)
> "Diversity is nowadays referred to as a heuristic with no precise definition" [Ver no PDF](zotero://open-pdf/library/items/ZGDT767X?page=2&annotation=G3LK2CPA)
> **Minha nota:** Teoricamente esse estudo definiu diversidade bem, e logo não é mais uma heuristica sem definição precisa

> [!warning] Definição (p. 5)
> "A theory of diversity would ideally have three key ingredients:  1. a definition of diversity as a measure of disagreement between the ensemble members; 2. this measure should have a clear relation to the overall ensemble error; and, 3. the theory should have a clear relation to previously established results, and expand  our understanding to a wider range of learning scenarios." [Ver no PDF](zotero://open-pdf/library/items/ZGDT767X?page=5&annotation=TUHQQZVC)
> **Minha nota:** Posso usar isso aqui na minha metodologia pra falar como eu posso derivar a diversidade para séries temporais.

> [!warning] Definição (p. 5)
> "The first point concerns the definition of diversity itself. An interesting question is whether the measure is a function solely of the ensemble member outputs, or whether it can involve the label distribution as well. Kuncheva (2014) refers to measures that rely on the true label as ‘oracle’ diversity measures. Both outcomes would be an interesting scientific conclusion: the label-independent case showing that diversity is solely a function of the ensemble itself, and the label-dependent case showing that it is a class-conditional phenomenon" [Ver no PDF](zotero://open-pdf/library/items/ZGDT767X?page=5&annotation=FE4LT7GU)
> **Minha nota:** Em regressão, a diversidade é independete do rótulo, por outro lado, na classificação, ela é dependente do rótulo e por definição é descritivo e redundante

> [!warning] Definição (p. 10)
> "This has decomposed the expected ensemble risk into: the noise, the average bias, the average variance, and the expected ambiguity. It is this expected ambiguity term that we consider as the ensemble diversity, which we highlight has the opposite sign to other terms." [Ver no PDF](zotero://open-pdf/library/items/ZGDT767X?page=10&annotation=GDUWVCHK)
> **Minha nota:** Ele generaliza a BVC em uma decomposição que

> [!warning] Definição (p. 10)
> "The ensemble combiner q is a centroid. In a practical scenario, the loss of the ensemble is chosen for whatever the task is: 0/1 loss, cross-entropy, or MSE, or many others. The combiner rule can also be chosen as almost anything: voting, arithmetic mean, weighted combinations, geometric mean, etc. The result above shows that, if we impose a constraint between these choices (i.e., Definition 4) we enable a decomposition which naturally exposes a diversity term. We emphasize that using this makes no claim on the empirical behavior of the ensemble, but simply on their theoretical properties" [Ver no PDF](zotero://open-pdf/library/items/ZGDT767X?page=10&annotation=JY92HTLJ)
> **Minha nota:** Eles afirmam que o centroide pode ser utilizado em qualque cenário, a regra de combinação também pode ser qualquer uma, porém eles afirmam que não existe declaração empirica que vai funcionar, apenas a propriedade teorica



## 2. Evidências que Apoiam a Tese (🟢)
> [!tip] Evidência / Resultado (p. 1)
> "prove a family of exact bias-variance-diversity decompositions, for a wide range of losses in both regression and classification, e.g., squared, cross-entropy, and Poisson losses." [Ver no PDF](zotero://open-pdf/library/items/ZGDT767X?page=1&annotation=SZW4K2SH)
> **Minha nota:** Provou uma familia de decomposições, eu quero tentar fazer o mesmo para a decomposição de séries temporais.

> [!tip] Evidência / Resultado (p. 1)
> "we should not be ‘maximising diversity’ as so many works aim to do—instead, we have a bias/variance/diversity trade-off to manage." [Ver no PDF](zotero://open-pdf/library/items/ZGDT767X?page=1&annotation=WPV6EJZH)
> **Minha nota:** Novamente fala que o ideal não é maximizar e sim gerenciar

> [!tip] Evidência / Resultado (p. 2)
> "There is, therefore, reason to pursue a unified theory, where diversity is derived from first principles" [Ver no PDF](zotero://open-pdf/library/items/ZGDT767X?page=2&annotation=DJKTH4RZ)
> **Minha nota:** Posso utillizar uma justificativa parecida para meu trabalho, visto que esse trabalho não deriva a diversidade para séries temporais

> [!tip] Evidência / Resultado (p. 2)
> "In contrast to previous efforts which define novel diversity measures, we take loss functions and decompose them, exposing terms that naturally account for diversity. We show that diversity is a hidden dimension in the bias-variance decomposition of the ensemble loss. In particular, we prove exact bias-variance-diversity decompositions, applying for a broad range of losses, taking a common form:  expected loss = (average bias) + (average variance) − (diversity),  where diversity is a measure of ensemble member disagreement, independent of the label" [Ver no PDF](zotero://open-pdf/library/items/ZGDT767X?page=2&annotation=4GKE8W99)
> **Minha nota:** Resultado do trabalho é que diversidade é uma dimensão escondida na decomposição da perda do ensemble. Eles pegaram a função de perda e decomporam ela. Possívelmente posso 
fazer o mesmo pro meu trabalho

> [!tip] Evidência / Resultado (p. 5)
> "Krogh and Vedelsby (1994) showed that, for an arithmetic mean combiner, using squared loss, the ensemble loss is guaranteed to be less than or equal to the average individual loss." [Ver no PDF](zotero://open-pdf/library/items/ZGDT767X?page=5&annotation=AW8T4GXA)
> **Minha nota:** Eles encontraram a definição para a perda  quadrada do ensemble utilizando média aritmética. Porém, consideram que os dados devem ser equilibrados e independentes (autocorrelação das séries temporais violam isso)

> [!tip] Evidência / Resultado (p. 5)
> "The second is known as the ambiguity—measuring the disagreement of individuals, as a spread around the ensemble prediction. Since this is non-negative, it guarantees the ensemble loss will be less than or equal to the average loss.  This result is often erroneously cited as the reason why all ensembles work. However, the form above applies only if we use the squared loss with an arithmetic mean combiner." [Ver no PDF](zotero://open-pdf/library/items/ZGDT767X?page=5&annotation=SV67FF49)
> **Minha nota:** Eles falam que a ambiguidade não é exatamente o porque todos os ensembles funcionam, mas eles dizem que é especificamente para o ensemble média aritmética com perda quadrada.

> [!tip] Evidência / Resultado (p. 5)
> "A deeper understanding came from Ueda and Nakano (1996)—though under the same loss/combiner assumptions. They extended the classical bias-variance theory of Geman et al. (1992) to show that the expected squared loss of the ensemble decomposes into three terms, involving the bias, variance, and covariance of the models. Here, the covariance captures the notion of ‘diversity’. More details on this will be provided later.  As mentioned, the expression above does not apply beyond squared loss with the arithmetic mean combiner." [Ver no PDF](zotero://open-pdf/library/items/ZGDT767X?page=5&annotation=9TBJZLMI)
> **Minha nota:** BVC aparece aqui de forma parecida com a ambiguidade, também só se aplica a perda quadrada com um ensemble com média aritmética



## 3. Pressupostos e Limitações (🔴)
> [!danger] Limitação / Pressuposto (p. 2)
> "However, here we encounter the problem of formally defining “diversity” and its relation to ensemble performance. In general, there is no agreement on how to quantify diversity, except in the limited case of regression with an arithmetic mean ensemble" [Ver no PDF](zotero://open-pdf/library/items/ZGDT767X?page=2&annotation=Q48VL6EY)
> **Minha nota:** Não existe um consenso em como quantificar a diversidade a não ser no caso de regressão com um ensemble de média aritmética



## 4. Desenho Experimental e Baselines (🔵)


## 5. Banco de Citações Diretas (🟣)


## 6. Dúvidas / Pontos para o Orientador (🟠 / ⚪)
> [!question] Discutir na Orientação (p. 1)
> "For losses where an additive bias-variance decomposition is not available (e.g., 0/1 loss) we present an alternative approach: quantifying the effects of diversity," [Ver no PDF](zotero://open-pdf/library/items/ZGDT767X?page=1&annotation=GJ3EKBBR)
> **Dúvida:** Didaci não tinha provado 0/1 loss no estudo deles?

> [!question] Discutir na Orientação (p. 2)
> "or losses where an additive biasvariance decomposition does not exist (e.g., 0/1 loss) we present an approach to precisely quantify the effects of diversity, with the caveat that the effects are conditional on the label distribution" [Ver no PDF](zotero://open-pdf/library/items/ZGDT767X?page=2&annotation=ZZV2SI5B)
> **Dúvida:** Didaci não tinha feito a decomposição para perda 0/1?

