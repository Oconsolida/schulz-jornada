# Schulz S.A. · A jornada de uma carga

Site de apresentação do diagnóstico e redesenho do processo de transporte da Schulz S.A.

**Apresentação:** 30 de abril de 2026
**Cliente:** Schulz S.A. (Joinville/SC)
**Elaboração:** Consolida + Lincros

## Sobre o projeto

Site estático de página única que apresenta a jornada de uma carga em 6 estações, do pedido ao pagamento, com diagnóstico AS IS, proposta TO BE e plano de implantação. Substitui a versão anterior do site de diagnóstico (que era organizada por área), trazendo storytelling orientado pela jornada da carga e por decisões executivas, mais adequado ao público de diretoria.

## Estrutura

```
schulz-jornada/
├── index.html              # Site completo (HTML + CSS + JS em um arquivo)
├── README.md               # Este arquivo
├── .gitignore              # Arquivos ignorados pelo Git
├── .nojekyll               # Desabilita Jekyll no GitHub Pages
├── docs/
│   └── diagnostico.md      # Documento mestre do diagnóstico (referência interna)
└── .github/
    └── workflows/
        └── deploy.yml      # Deploy automático para GitHub Pages
```

## Arquitetura do conteúdo

O site tem 8 seções principais:

1. **Hero** — Capa com tese central
2. **Panorama** — 3 estatísticas que dimensionam o problema
3. **Jornada** — 6 estações em scroll horizontal (pedido entra, contratada, sai, viaja, entregue, pago)
4. **O fio invisível** — Diagrama interativo Hoje vs Redesenho
5. **A peça invisível** — Governança contratual da malha
6. **3 decisões executivas** — CTA pra diretoria
7. **Cronograma** — Sistema e Governança em swimlanes paralelas
8. **5 indicadores** — Comparativo Hoje vs Meta 90 dias

## Tecnologia

Site 100% estático, sem dependências de build. HTML + CSS + JavaScript vanilla em um único arquivo. Fontes carregadas via Google Fonts CDN.

- **Tipografia:** Plus Jakarta Sans (texto) + JetBrains Mono (labels técnicas)
- **Cores:** Roxo Consolida (#5B45F5) + Cyan (#00B8B8) + base off-white
- **Animações:** IntersectionObserver para reveal on scroll, contadores animados, scroll snap horizontal
- **Acessibilidade:** Navegação por teclado (setas, espaço, page up/down) e por botões clicáveis

## Como rodar localmente

```bash
# Não requer build. Basta abrir o arquivo no navegador:
open index.html

# Ou rodar um servidor estático simples se preferir:
python3 -m http.server 8000
# Acesse http://localhost:8000
```

## Como publicar

O site é publicado automaticamente no GitHub Pages a cada push na branch `main`, via GitHub Actions. URL final:

```
https://oconsolida.github.io/schulz-jornada/
```

Configuração necessária no repositório (faz uma vez só):

1. Ir em **Settings → Pages**
2. Em **Source**, selecionar **GitHub Actions**
3. Confirmar que o workflow `.github/workflows/deploy.yml` está ativo

## Histórico

- **v1.0** (mar/2026): Diagnóstico organizado por área, em apresentação .pptx
- **v2.0** (abr/2026): Site web organizado por dores e processos
- **v3.0** (atual): Redesenho completo com storytelling pela jornada da carga

## Contato

**Diego Araújo** · Consolida
diego@oconsolida.com · 47 98433 5969
