# Guia de conversao do site-mavi.html para template editavel no Elementor Pro

Este guia organiza o HTML unico em um template One Page do Elementor, mantendo os mesmos blocos e estilos, mas com edicao visual.

## 1) Preparacao (Elementor Pro)

1. Crie uma pagina nova e escolha o modelo **Elementor Canvas** (sem header/rodape do tema).
2. Em **Elementor > Configuracoes do site**, defina:
   - **Cores globais** (baseadas nas variaveis CSS).
   - **Tipografia global** (Fraunces para titulos e Inter para texto).
3. (Opcional) Ative o **Custom CSS** do Elementor Pro para aplicar ajustes finos.

### Paleta recomendada (cores globais)
Use estas cores como referencia no Site Settings:

- Ink: `#121212`
- Paper: `#F6F2EA`
- Paper 2: `#EFE9DE`
- Cement: `#D7D3CC`
- Stone: `#BDB8AF`
- Moss 950: `#1E261E`
- Moss 900: `#2F3A2E`
- Moss 800: `#384538`
- Moss 700: `#465846`
- Moss 200: `#D9E3D7`
- Moss 120: `#EAF1E7`
- Lemon 50: `#FFF9DB`
- Lemon 100: `#FFF3BF`
- Lemon 200: `#FFE88A`
- Lemon 500: `#F5D547`
- Lemon 700: `#C9A900`

### Tipografia global
- Titulos: **Fraunces** (400/600)
- Texto: **Inter** (300/400/500/600)

## 2) Estrutura recomendada no Elementor (mapa de secoes)

Abaixo esta o mapeamento direto do HTML para secoes e widgets do Elementor.

### Header (fixo)
**HTML equivalente:** `header.nav` com links de ancoragem.

- **Section (Full Width)** com colunas 2 (logo + links).
- Em **Avancado > Motion Effects**, habilite **Sticky: Top**.
- Fundo: `rgba(246, 242, 234, 0.78)`.
- Links apontando para as ancoras (#mavi, #colecao, #produtos, #ritual).

### Section 1 - Hero (id: topo)
**HTML equivalente:** `section.hero` com titulo, texto, botoes e ilustracao.

- Section com duas colunas.
- Coluna 1: Eyebrow, H1, texto, botoes (WhatsApp + CTA).
- Coluna 2: mock visual da vela.
  - Pode usar uma imagem ilustrativa ou criar uma caixa com background e borda arredondada.

### Section 2 - Manifesto (id: mavi)
**HTML equivalente:** `section.manifesto`.

- Section com fundo `#D9E3D7` e card interno.
- Duas colunas: texto institucional + bloco de quote.
- Para o quote, use um widget de texto com `font-style: italic` e negrito interno.

### Section 3 - Triad Experience
**HTML equivalente:** `section.neutral` com 3 tiles.

- Section com fundo `#EFE9DE`.
- Titulo + texto.
- 3 colunas (cada uma com icon + titulo + texto).
- Icons: usar **Icon** ou **HTML widget** para inserir SVGs.

### Section 4 - How it is made
**HTML equivalente:** `section.neutral section--tight` com split.

- Section com duas colunas.
- Coluna 1: texto “Feito a mao”.
- Coluna 2: lista com bullets (Text Editor + Icon List).

### Section 5 - Packaging
**HTML equivalente:** `section.neutral section--tight`.

- Section simples com titulo + texto.

### Section 6 - Collection intro (id: colecao)
**HTML equivalente:** `section.lemon`.

- Section com fundo em gradiente `#FFF3BF` -> `#FFE88A`.
- Badge com icone e texto (pode usar **Icon + Text**).
- CTA principal para WhatsApp.

### Section 7 - Sensation map
**HTML equivalente:** `section.lemon section--tight`.

- Section com fundo claro.
- Use 3 colunas com “chips” (cada um: titulo + subtitulo + texto).

### Section 8 - Produtos (id: produtos)
**HTML equivalente:** `section.products`.

- Section com titulo + texto.
- Grid de 2 ou 3 colunas (cards).
- Cada card: nome, tag, descricao e botao WhatsApp.
- Use o widget **Inner Section** ou **Containers** para repetir cards.

### Section 9 - Ritual (id: ritual)
**HTML equivalente:** `section.neutral section--tight`.

- Section com titulo + texto.
- 3 colunas com numeracao (1,2,3) e texto.

### Footer
**HTML equivalente:** `footer.footer`.

- Section com fundo `#2F3A2E`.
- Duas colunas: logo + texto, e links de ancoragem.
- Texto final com ano.

### Botao flutuante do WhatsApp
- Use **Elementor > Custom Code** ou um plugin de **Floating Button**.
- Link apontando para `https://wa.me/55SEUNUMEROAQUI`.

## 3) Onde colocar o CSS

### Opcao A (Recomendada): Site Settings > Custom CSS
Cole apenas ajustes finais (ex: sombras, bordas, radius, background).

### Opcao B: CSS em cada secao
Use **Avancado > CSS Personalizado** em cada Section/Widget para detalhes isolados.

### CSS sugerido para o Header (template JSON)
Se importar o arquivo `elementor-header-template.json`, aplique este CSS no **Site Settings > Custom CSS**
para alinhar o visual ao HTML original:

```css
.mavi-header{
  backdrop-filter: blur(12px);
}
.mavi-header .elementor-container{
  align-items: center;
}
.mavi-brand{
  display: inline-flex;
  align-items: baseline;
  gap: 10px;
  font-family: "Fraunces", ui-serif, Georgia, "Times New Roman", serif;
  letter-spacing: -0.01em;
}
.mavi-brand__mark{
  width: 10px;
  height: 10px;
  border-radius: 50%;
  background: linear-gradient(180deg, #465846, #2F3A2E);
  box-shadow: 0 0 0 5px rgba(70, 88, 70, 0.12);
  flex: 0 0 auto;
  transform: translateY(-1px);
}
.mavi-brand__name{
  font-weight: 600;
  font-size: 1.15rem;
}
.mavi-brand__tag{
  font-family: "Inter", ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif;
  font-weight: 500;
  font-size: 0.95rem;
  opacity: 0.65;
  margin-left: 10px;
}
.mavi-nav{
  display: flex;
  gap: 18px;
  align-items: center;
  justify-content: flex-end;
  font-weight: 500;
  font-size: 0.95rem;
}
.mavi-nav a{
  padding: 8px 10px;
  border-radius: 999px;
  opacity: 0.86;
  transition: background 0.25s ease, opacity 0.25s ease;
}
.mavi-nav a:hover{
  background: rgba(0, 0, 0, 0.05);
  opacity: 1;
}
@media (max-width: 960px){
  .mavi-nav{
    display: none;
  }
}
```

## 4) Checklist de conversao

- [ ] Criar pagina One Page com ancoras (#topo, #mavi, #colecao, #produtos, #ritual)
- [ ] Definir cores e tipografias globais
- [ ] Recriar secoes na mesma ordem do HTML
- [ ] Substituir SVG por icones do Elementor ou HTML widget
- [ ] Configurar botoes com links WhatsApp
- [ ] Ajustar responsivo (tablet e mobile)

## 5) Dica final
Depois de pronto, salve como **Template > Page** para reutilizar em outros projetos.

---

Arquivo base: `site-mavi.html`.
