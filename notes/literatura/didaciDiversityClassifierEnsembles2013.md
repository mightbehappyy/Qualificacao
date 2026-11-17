---
autores: Luca Didaci, Giorgio Fumera, Fabio Roli
ano: "2013"
titulo: "Diversity in Classifier Ensembles: Fertile Concept or Dead End?"
chave_citacao: "@didaciDiversityClassifierEnsembles2013"
tags:
  - fichamento
  - ensemble
  - diversidade
  - series-temporais
status: lido
---

# Diversity in Classifier Ensembles: Fertile Concept or Dead End? (2013)
- **Zotero:** [Abrir PDF no Zotero]([Didaci et al. - 2013 - Diversity in Classifier Ensembles Fertile Concept or Dead End.pdf](zotero://select/library/items/WPZ5B787))

## Síntese em 3 linhas
Didaci discute no artigo uma nova definição do erro de ensembles para classificação com problemas com mais de 2 classes. Ele também explora o conceito de "boa" e "má" diversidade, esse conceito basicamente ocorre da seguinte forma, a diversidade reduz o erro quando o ensemble acerta, isso é chamado de diversidade boa, quando o ensemble erra, é chamado de má diversidade. Uma das conclusões é que as métricas de diversidade existentes são apenas uma aproximação do termo da diversidade real e que há poucos cenários em que ela possa ser usada explicitamente. Também afirmam que na prática, a definição serve mais para uma explicação de como a diversidade funciona do que uma métrica para ser utilizada na construção do ensemble.

---

## 1. Definições e Conceitos (🟡)
> [!warning] Definição (p. 37)
> "wide empirical evidence motivates the potential usefulness of combining non-identical classifiers. This lead to the widely accepted idea that: (i) there exists a property of MCSs that can be defined as “diversity”" [Ver no PDF](zotero://open-pdf/library/items/WPZ5B787?page=37&annotation=WA9TBEEH)
> **Minha nota:** Existe uma propriedade chamada diversidade que pode ser  definida quantitativamente e dessa forma, mensurada que é relaciionada com a acurácia do ensemble

> [!warning] Definição (p. 43)
> "RHS of decomposition (11) can be interpreted as a diversity measure," [Ver no PDF](zotero://open-pdf/library/items/WPZ5B787?page=43&annotation=3GPTTLTU)
> **Minha nota:** Métrica de diversidade proposta pelo estudo

> [!warning] Definição (p. 43)
> "However, for L > 2 the disagreement is not expressed in terms of the class labels, but in terms of the correctness of such choices (they coincide only when L = 2)." [Ver no PDF](zotero://open-pdf/library/items/WPZ5B787?page=43&annotation=VE8C6HUR)

> [!warning] Definição (p. 43)
> "eens(d) = e(d) −  ∫  x+  1 N  N ∑ j=1  δj(x; d)dx +  ∫  x−  1 N  N ∑ j=1  δj(x; d)dx ." [Ver no PDF](zotero://open-pdf/library/items/WPZ5B787?page=43&annotation=VVS6I6T3)
> **Minha nota:** Trazem uma definição de boa e má diversidade

> [!warning] Definição (p. 44)
> "the more we involve the ensemble performance into defining diversity, the more we are running onto the risk of trying to replace a simple" [Ver no PDF](zotero://open-pdf/library/items/WPZ5B787?page=44&annotation=NXDBJJSN)
> **Minha nota:** <b>Wood et al.</b> mostra que a saída para esse impasse na regressão (sob perda quadrática e média aritmética) é justamente a <b>ambiguidade</b>: ela é "pura" (independe do rótulo $y$), mas, por ser derivada exatamente da função de perda e da regra de combinação (centroide), possui uma ligação matemática exata com a redução do erro esperado

> [!warning] Definição (p. 45)
> "Diversity is measured as the average pairwise disagreement between individual classifiers." [Ver no PDF](zotero://open-pdf/library/items/WPZ5B787?page=45&annotation=ASLA4ITL)


> [!warning] Definição (p. 45)
> "To sum up, existing diversity measures are at most an approximation of the “real” diversity term, in the context of exact decompositions of the ensemble error like (14) and (11)" [Ver no PDF](zotero://open-pdf/library/items/WPZ5B787?page=45&annotation=LNYZ9DTK)
> **Minha nota:** Os termos de diversidade apenas se aproximam do termo real da diversidade (que seria o que ele propôs)



## 2. Evidências que Apoiam a Tese (🟢)
> [!tip] Evidência / Resultado (p. 37)
> "such a property can be practically exploited to construct an effective ensemble of classifiers." [Ver no PDF](zotero://open-pdf/library/items/WPZ5B787?page=37&annotation=LT7DAEW7)
> **Minha nota:** Essa propriedade pode ser explorada para contruir um ensemble

> [!tip] Evidência / Resultado (p. 40)
> "From the practical viewpoint of ensemble construction, the ambiguity decomposition was successfully exploited by the Negative Correlation Learning (NCL) method [25].3" [Ver no PDF](zotero://open-pdf/library/items/WPZ5B787?page=40&annotation=WLGMWMJ4)


> [!tip] Evidência / Resultado (p. 43)
> "This highlights that increasing the disagreement is beneficial on samples where the ensemble is correct, while it is detrimental on samples where the ensemble is wrong." [Ver no PDF](zotero://open-pdf/library/items/WPZ5B787?page=43&annotation=K3ZXKN36)
> **Minha nota:** Validar isso aqui é importante no meu projeto

> [!tip] Evidência / Resultado (p. 44)
> "However, even though computing the ambiguity term in (6) is not computationally cheaper than directly computing the ensemble MSE, the former does not involve the correct output y, which allows one to compute it using also unlabelled samples." [Ver no PDF](zotero://open-pdf/library/items/WPZ5B787?page=44&annotation=QFM7DZI6)
> **Minha nota:** No instante t eu ainda não sei y_t+h, mas consigo calcular a diversidade com a previsão dos modelos



## 3. Pressupostos e Limitações (🔴)
> [!danger] Limitação / Pressuposto (p. 38)
> "existing measures reflect intuitive notions of diversity, none of them has been derived from an exact decomposition of the ensemble error," [Ver no PDF](zotero://open-pdf/library/items/WPZ5B787?page=38&annotation=T7M2IP7V)


> [!danger] Limitação / Pressuposto (p. 38)
> "contrary to the ambiguity decomposition; none of them exhibits a clear trade-off with the average error of ensemble members" [Ver no PDF](zotero://open-pdf/library/items/WPZ5B787?page=38&annotation=EF3FGS5G)


> [!danger] Limitação / Pressuposto (p. 40)
> "could also be exploited in the context of an overproduce and choose strategy, for selecting the best subset of regressors s′ out of a given, larger set s. The members of s can be first independently trained (by minimising their individual MSE); then, the subset s′ exhibiting the highest ambiguity should be selected. However, all works on regressor ensemble selection we are aware of did not use this approach, but relied on the direct estimate of the ensemble MSE" [Ver no PDF](zotero://open-pdf/library/items/WPZ5B787?page=40&annotation=UAQM99UV)
> **Minha nota:** Possível limitação que eu possa explorar. Mas basicamente isso é seleção dinâmica na série temporal.



## 4. Desenho Experimental e Baselines (🔵)
> [!info] Método / Métrica / Baseline (p. 38)
> "deriving exact decompositions of the ensemble error for any combining rule and any number of classes; and exploiting them to understand" [Ver no PDF](zotero://open-pdf/library/items/WPZ5B787?page=38&annotation=24QQIILQ)
> **Minha nota:** Aqui eles tentam trazer a decomposição para espeficiamente classificação. No meu caso eu posso usar algo parecido mas para séries temporal e falar sobre não estacionariedade e autocorrelação

> [!info] Método / Métrica / Baseline (p. 38)
> "whether they can provide a more clear understanding of diversity" [Ver no PDF](zotero://open-pdf/library/items/WPZ5B787?page=38&annotation=QJAIJHIK)
> **Minha nota:** Esse número dois é bem vago, tentar definir melhor nos meus objetivos

> [!info] Método / Métrica / Baseline (p. 38)
> "whether they can be exploited for ensemble construction, more effectively than existing measures" [Ver no PDF](zotero://open-pdf/library/items/WPZ5B787?page=38&annotation=G9E9DFUY)
> **Minha nota:** Posso ser bem especifico aqui sobre como posso construir o ensemble, mais especificamente para seleção dinâmica.



## 5. Banco de Citações Diretas (🟣)
> [!quote] Citação (p. 39)
> "ED[(fens − E[Y |x])2] = bias2 + 1  N var + (1 − 1  N )cov ." [Ver no PDF](zotero://open-pdf/library/items/WPZ5B787?page=39&annotation=WVEZKPX9)
> **Nota:** Formula vies e variancia com diversidade

> [!quote] Citação (p. 39)
> "1  N  N ∑ i=1  (fi − fens)2" [Ver no PDF](zotero://open-pdf/library/items/WPZ5B787?page=39&annotation=FQSIEGPV)


> [!quote] Citação (p. 39)
> "(y − fens)2 = 1  N  N ∑ i=1  (y − fi)2 − 1  N  N ∑ i=1  (fi − fens)2 ." [Ver no PDF](zotero://open-pdf/library/items/WPZ5B787?page=39&annotation=XWXBJWV3)
> **Nota:** erro do comitê = média dos erros individuais - diversidade (ambiguidade)

> [!quote] Citação (p. 39)
> "Therefore, this provides a clear, formal definition of “diversity” for regression problems" [Ver no PDF](zotero://open-pdf/library/items/WPZ5B787?page=39&annotation=D2E5DDBM)
> **Nota:** Definição formal de diversidade para problemas de diversidade, porém isso não leva em consideração as especificadades de séries temporais.

> [!quote] Citação (p. 40)
> "concept of covariance is undefined for categorical outputs" [Ver no PDF](zotero://open-pdf/library/items/WPZ5B787?page=40&annotation=USFMR5JH)
> **Nota:** Para regressão, não é indefinido

> [!quote] Citação (p. 40)
> "In the following we show how an analogue of the BVC decomposition can be derived, as well as the analogue of the ambiguity decomposition" [Ver no PDF](zotero://open-pdf/library/items/WPZ5B787?page=40&annotation=44QLMBPA)
> **Nota:** Eles se baseiam na decomposição da ambiguidade

> [!quote] Citação (p. 42)
> "eens(x) = e(x) − ∑  yi P [yi] 1  N  ∑  j  (Pˆens[yi] − Pˆj [yi]  )  = e(x) − 1  N  ∑  j  (PD,Y |x[fens = Y |x] − PD,Y |x[fj = Y |x]) ." [Ver no PDF](zotero://open-pdf/library/items/WPZ5B787?page=42&annotation=NVUAYR32)
> **Nota:** Avalia o desempenho teórico do esperado do ensemble ao longo de multiplos treinamentos possíveis

> [!quote] Citação (p. 42)
> "eens(x; d) = e(x; d) − 1  N  ∑  j  (PY |x[fens = Y |x] − PY |x[fj = Y |x]) ." [Ver no PDF](zotero://open-pdf/library/items/WPZ5B787?page=42&annotation=TJIP7H48)
> **Nota:** Avalia o erro esperado de um comitê já treinado diante do ruído das classes de x

> [!quote] Citação (p. 42)
> "efens (x, y; d) = e(x, y; d) − 1  N  ∑  j  (I[fens = y] − I[fj = y]) ." [Ver no PDF](zotero://open-pdf/library/items/WPZ5B787?page=42&annotation=YD4HQNAA)
> **Nota:** Todos os componentes são fixos (Entrada, rótulo y e treino) Mede o ganho ou perda de um ensemble em um único exemplo de teste, serve também pra validar quando existe má e boa diversidade



## 6. Dúvidas / Pontos para o Orientador (🟠 / ⚪)
> [!question] Discutir na Orientação (p. 43)
> "Can the second term of decomposition (12)–(14) be interpreted as a diversity measure? Can it be practically exploited for ensemble construction?" [Ver no PDF](zotero://open-pdf/library/items/WPZ5B787?page=43&annotation=XN4F835T)


