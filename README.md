# 🗺️ Mapa dos Bairros de Castanhal (PA)

Mapa **interativo** dos bairros de Castanhal, no Pará, com **cores distintas** e **nomes**
para cada bairro e navegação **estilo Google Maps** (zoom, arraste, satélite).

👉 **Página do mapa:** `index.html` (abra no navegador ou publique no GitHub Pages).

## ✨ Recursos

- **Zoom/pan estilo Google Maps** (Leaflet): roda do mouse, `+/−`, duplo-clique e arraste.
- **Cada bairro em um polígono colorido e nomeado** — cor distinta por bairro (paleta
  por ângulo áureo em HSL) e rótulo com o nome.
- **Dados ao vivo do OpenStreetMap (+ complemento por geocodificação)** — ao abrir, a
  página consulta a [Overpass API](https://overpass-api.de/) para pegar os bairros
  mapeados no OSM e **completa os oficiais que faltam** (ex.: Estrela, Milagre)
  geocodificando-os pelo [Nominatim](https://nominatim.org/), restrito à área de
  Castanhal. Cada bairro vira um polígono por **partição de Voronoi** (área de influência
  do ponto), recortada pelo **fecho convexo** dos bairros (cobertura contígua, sem vãos)
  e pelo limite do município.
- **Dois mapas base alternáveis:** Ruas (OpenStreetMap) e Satélite (Esri World Imagery).
- **Legenda clicável** — lista os bairros; clicar centraliza e dá zoom no bairro.
- **Modo de emergência** — se a Overpass estiver indisponível, exibe posições
  aproximadas de referência para não deixar o mapa vazio.

## 🚀 Como usar

### Opção 1 — abrir localmente
Basta abrir o arquivo `index.html` em qualquer navegador moderno com internet
(os mapas e os dados do OpenStreetMap são carregados online).

### Opção 2 — publicar no GitHub Pages
1. Vá em **Settings → Pages** do repositório.
2. Em **Build and deployment → Source**, selecione **Deploy from a branch**.
3. Escolha a branch (ex.: `main`) e a pasta `/ (root)` e salve.
4. Em alguns instantes o mapa estará em
   `https://<seu-usuario>.github.io/mapa-bairros-castanhal/`.

## 🧩 Tecnologia

- [Leaflet](https://leafletjs.com/) — mapa e interação.
- [Turf.js](https://turfjs.org/) — partição de Voronoi e recorte dos polígonos.
- [osmtogeojson](https://github.com/tyrasd/osmtogeojson) — conversão da resposta Overpass.
- [OpenStreetMap](https://www.openstreetmap.org/) — dados dos bairros e tiles de ruas.
- [Esri World Imagery](https://www.arcgis.com/) — camada de satélite.

Sem build, sem dependências locais: é uma **única página HTML autônoma**.

## 📝 Observações sobre os dados

- Castanhal possui **28 bairros oficiais** (Lei nº 029/2019) mais o distrito de Apeú.
  O OpenStreetMap pode listar variações/nomes adicionais; o mapa unifica duplicidades
  (maiúsculas/acentos) automaticamente.
- **Sobre os limites:** o OpenStreetMap tem o **contorno oficial** de apenas alguns
  bairros de Castanhal. Para todos os outros, os polígonos exibidos são uma
  **aproximação por Voronoi** (a partir do ponto de cada bairro), **não** os limites
  legais. Servem para visualização, não para uso cadastral. Contribua com os contornos
  reais em [openstreetmap.org](https://www.openstreetmap.org/) para melhorar o mapa —
  a página passa a usá-los automaticamente assim que existirem.

## 📄 Licença

MIT. Dados © colaboradores do OpenStreetMap.
