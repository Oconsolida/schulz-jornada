# Prompt para Claude Code · Publicação do site Schulz Jornada

Cole o conteúdo abaixo no Claude Code dentro da pasta onde você descompactou o projeto `schulz-jornada/`. O Claude Code vai executar tudo: criar repositório, fazer commit, push, configurar GitHub Pages e te entregar o link final.

---

## INSTRUÇÕES PARA O CLAUDE CODE

Você está dentro da pasta de um projeto chamado `schulz-jornada`. Execute as etapas abaixo na ordem, parando para me pedir confirmação se algum passo precisar de credencial ou autorização.

### Contexto do projeto

Site estático de uma página única (`index.html`) que apresenta o diagnóstico de logística da Schulz S.A. para apresentação de 30 de abril de 2026. O cliente da Consolida é Diego Araújo (CEO, diego@oconsolida.com). O repositório anterior está em https://github.com/Oconsolida/schulz-diagnostico, este é uma versão completamente redesenhada e deve ir para um repositório novo chamado `schulz-jornada`.

### Etapa 1 · Verificar estrutura local

Rode `ls -la` e confirme que existem os seguintes arquivos:

```
schulz-jornada/
├── index.html              (site principal, deve ter ~65KB)
├── README.md
├── .gitignore
├── .nojekyll               (arquivo vazio, importante)
├── docs/
│   └── diagnostico.md
└── .github/
    └── workflows/
        └── deploy.yml
```

Se algum arquivo estiver faltando, pare e me avise. **Não edite nem regenere os arquivos**, eles estão na forma final que o Diego aprovou.

### Etapa 2 · Inicializar Git localmente

```bash
git init
git branch -M main
git add .
git commit -m "Initial commit: site jornada da carga Schulz"
```

Se já estiver inicializado, apenas adicione e commite as mudanças.

### Etapa 3 · Criar repositório no GitHub

Use o GitHub CLI (`gh`) se estiver disponível:

```bash
gh repo create Oconsolida/schulz-jornada --public --source=. --remote=origin --push
```

Se o `gh` não estiver autenticado, peça ao Diego para rodar `gh auth login` antes.

Se o `gh` não estiver instalado, **pare e me avise**, mostre o comando alternativo via API ou peça ao Diego para criar o repositório manualmente em github.com/new com:
- Nome: `schulz-jornada`
- Owner: `Oconsolida`
- Visibilidade: Public
- **Não** inicializar com README (já temos um)

Depois rode:
```bash
git remote add origin https://github.com/Oconsolida/schulz-jornada.git
git push -u origin main
```

### Etapa 4 · Configurar GitHub Pages

O workflow `.github/workflows/deploy.yml` faz deploy automático, mas precisa que o GitHub Pages esteja configurado para usar GitHub Actions como fonte. Configure via API ou avise o Diego para fazer manualmente:

**Configuração manual (caminho seguro):**
1. Abrir https://github.com/Oconsolida/schulz-jornada/settings/pages
2. Em **Source**, selecionar **GitHub Actions**
3. Salvar

**Configuração via API (se tiver token com permissão de admin no repo):**
```bash
gh api -X POST /repos/Oconsolida/schulz-jornada/pages \
  -f "source[branch]=main" \
  -f "source[path]=/" \
  -f "build_type=workflow"
```

### Etapa 5 · Acompanhar deploy

Após o push, o workflow do GitHub Actions vai rodar automaticamente. Você pode acompanhar com:

```bash
gh run watch
```

Ou abrir https://github.com/Oconsolida/schulz-jornada/actions no navegador.

O deploy normalmente leva 1 a 2 minutos. Quando finalizar, o site fica disponível em:

```
https://oconsolida.github.io/schulz-jornada/
```

### Etapa 6 · Validar publicação

1. Aguardar o workflow finalizar com sucesso (status verde).
2. Abrir a URL final no navegador.
3. Verificar se o site carrega completo, com:
   - Hero com fundo branco e gradiente de pontos roxos
   - Stats animados (R$ 58M, 7 portais, 30%)
   - Seção da jornada com fundo escuro e scroll horizontal funcionando
   - Toggle "Hoje / Com o redesenho" funcionando na seção do fio
   - Footer escuro com gradiente roxo no título

Se algo não carregar, o problema mais provável é cache do GitHub Pages. Aguardar 5 minutos e tentar de novo. Se persistir, abrir o DevTools e ver se há erro no console.

### Etapa 7 · Me devolver

Quando tudo estiver no ar, me retorne:

1. URL do repositório no GitHub
2. URL pública do site
3. Status do último workflow (verde / vermelho)
4. Qualquer observação relevante (se precisou intervenção manual em algum passo)

Se algum erro acontecer, **pare e me explique o que aconteceu antes de tentar corrigir sozinho**.

---

## Observações importantes

- O arquivo `.nojekyll` é fundamental, ele impede que o GitHub Pages tente processar o HTML com Jekyll, o que quebraria o site.
- O workflow já está configurado para rodar a cada push na main, então qualquer atualização futura é automática.
- O domínio personalizado pode ser configurado depois (ex: `schulz.oconsolida.com.br`) via Settings → Pages → Custom domain. Por ora, fica na URL `github.io`.
- Se o Diego quiser, podemos depois mover esse projeto pra dentro de uma estrutura monorepo `consolida-sites/schulz-jornada`, mas por ora repositório isolado é mais simples.
