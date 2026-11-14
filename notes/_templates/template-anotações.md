---
autores: "{{authors}}"
ano: {{date | format("YYYY")}}
titulo: "{{title}}"
chave_citacao: "@{{citekey}}"
tags: [fichamento, ensemble, diversidade, series-temporais]
status: lido
---

# {{title}} ({{date | format("YYYY")}})
- **Zotero:** [Abrir PDF no Zotero]({{pdfZoteroLink}})

## Síntese em 3 linhas
*(Preencher após importar)*

---

## 1. Definições e Conceitos (🟡)
{% for annotation in annotations -%}
{%- if annotation.color == "#ffd400" -%}
> [!warning] Definição (p. {{annotation.pageLabel}})
> "{{annotation.annotatedText}}" [Ver no PDF]({{annotation.desktopURI}})
{% if annotation.comment %}> **Minha nota:** {{annotation.comment}}{% endif %}

{% endif -%}
{%- endfor %}

## 2. Evidências que Apoiam a Tese (🟢)
{% for annotation in annotations -%}
{%- if annotation.color == "#5fb236" -%}
> [!tip] Evidência / Resultado (p. {{annotation.pageLabel}})
> "{{annotation.annotatedText}}" [Ver no PDF]({{annotation.desktopURI}})
{% if annotation.comment %}> **Minha nota:** {{annotation.comment}}{% endif %}

{% endif -%}
{%- endfor %}

## 3. Pressupostos e Limitações (🔴)
{% for annotation in annotations -%}
{%- if annotation.color == "#ff6666" -%}
> [!danger] Limitação / Pressuposto (p. {{annotation.pageLabel}})
> "{{annotation.annotatedText}}" [Ver no PDF]({{annotation.desktopURI}})
{% if annotation.comment %}> **Minha nota:** {{annotation.comment}}{% endif %}

{% endif -%}
{%- endfor %}

## 4. Desenho Experimental e Baselines (🔵)
{% for annotation in annotations -%}
{%- if annotation.color == "#2ea8e5" -%}
> [!info] Método / Métrica / Baseline (p. {{annotation.pageLabel}})
> "{{annotation.annotatedText}}" [Ver no PDF]({{annotation.desktopURI}})
{% if annotation.comment %}> **Minha nota:** {{annotation.comment}}{% endif %}

{% endif -%}
{%- endfor %}

## 5. Banco de Citações Diretas (🟣)
{% for annotation in annotations -%}
{%- if annotation.color == "#a28ae5" -%}
> [!quote] Citação (p. {{annotation.pageLabel}})
> "{{annotation.annotatedText}}" [Ver no PDF]({{annotation.desktopURI}})
{% if annotation.comment %}> **Nota:** {{annotation.comment}}{% endif %}

{% endif -%}
{%- endfor %}

## 6. Dúvidas / Pontos para o Orientador (🟠 / ⚪)
{% for annotation in annotations -%}
{%- if annotation.color == "#f19837" or annotation.color == "#aaaaaa" -%}
> [!question] Discutir na Orientação (p. {{annotation.pageLabel}})
> "{{annotation.annotatedText}}" [Ver no PDF]({{annotation.desktopURI}})
{% if annotation.comment %}> **Dúvida:** {{annotation.comment}}{% endif %}

{% endif -%}
{%- endfor %}