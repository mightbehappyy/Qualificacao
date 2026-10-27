---
citekey: "{{citekey}}"
titulo: "{{title}}"
ano: 'ano: "{% if date %}{{date | format("YYYY")}}{% endif %}"'
autores: "{% for c in creators %}{{c.lastName}}, {{c.firstName}}{% if not loop.last %}; {% endif %}{% endfor %}"
tags:
  - literatura
status: nao-lido
---
# {{title}}

{% if desktopURI %}[Abrir no Zotero]({{desktopURI}}){% endif %}

## Minhas notas
{% persist "notas" %}
**Ideia central:**

**Relevância para a qualificação:**

**Críticas / limitações:**

**Conceitos relacionados:** [[ ]]
{% endpersist %}

## Anotações do PDF
{% for annotation in annotations %}
- {{annotation.annotatedText}}{% if annotation.pageLabel %} (p. {{annotation.pageLabel}}){% endif %}
  {% if annotation.comment %}→ {{annotation.comment}}{% endif %}
{% endfor %}