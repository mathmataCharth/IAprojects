# IAprojects – Template Elementor (Mavi Casa)

Este repositório contém materiais para converter o site One Page `site-mavi.html` em um template editável no Elementor Pro.

## O que tem aqui

- **`site-mavi.html`**: arquivo base do layout One Page original.
- **`elementor-template-plan.md`**: guia de conversão com o mapeamento de seções e widgets do Elementor.
- **`elementor-header-template.json`**: template JSON da seção **Header** (pronto para importar no Elementor).

## Como usar

1. **Importar o Header**
   - No Elementor, vá em **Templates > Importar Templates**.
   - Importe o arquivo `elementor-header-template.json`.

2. **Aplicar o CSS do Header**
   - Siga o CSS sugerido no arquivo `elementor-template-plan.md` para o Header.
   - Cole em **Elementor > Site Settings > Custom CSS**.

3. **Recriar as demais seções**
   - Use o guia em `elementor-template-plan.md` para montar cada seção do One Page.

## Requisitos

- WordPress com **Elementor Pro** (para importação de template e CSS global).

## Observações

- Os links de âncora usados no One Page são: `#topo`, `#mavi`, `#colecao`, `#produtos`, `#ritual`.
- O botão flutuante de WhatsApp pode ser implementado via **Elementor > Custom Code** ou plugin dedicado.
