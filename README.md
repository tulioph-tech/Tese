# Tese de Doutorado - Rigidez Dinamica de Suportes Viscoelasticos

Repositorio unico da tese: texto (LaTeX), scripts (MATLAB/APDL), dados, figuras e referencias.

```
tese-viscoelastic/
|-- AGENTS.md              regras para IAs (Claude, ChatGPT/Codex)
|-- CLAUDE.md              aponta para AGENTS.md + CONTEXTO.md (Claude Code)
|-- docs/
|   |-- CONTEXTO.md        resumo da tese, notacao, etapas
|   |-- decisoes.md        log de decisoes metodologicas
|-- tex/
|   |-- main.tex           documento principal (usa ppginf.cls se estiver na pasta)
|   |-- preambulo.tex      pacotes + macros de notacao
|   |-- pretextuais.tex    capa, resumo etc. do template UFPR
|   |-- capitulos/         cap01 ... cap07
|   |-- referencias.bib    GERADO PELO MENDELEY
|-- matlab/                scripts de calculo e geracao de figuras
|-- ansys/                 APDL / inputs (sem arquivos de resultado)
|-- dados/brutos/          dados de ensaio (somente leitura)
|-- dados/processados/     saidas dos scripts
|-- figuras/               PDFs gerados por script
```

---

## Passo 1 - Criar o repositorio no GitHub

1. Em github.com: **New repository** > nome `tese-viscoelastic` > **Private** > *sem* README.
2. No computador, dentro desta pasta:
   ```
   git init
   git add .
   git commit -m "Estrutura inicial da tese"
   git branch -M main
   git remote add origin https://github.com/SEU_USUARIO/tese-viscoelastic.git
   git push -u origin main
   ```
3. Copie seu `ppginf.cls` (e arquivos auxiliares do template) para `tex/` e o conteudo pre-textual
   para `tex/pretextuais.tex`. Commit.
4. (Opcional) Adicione o orientador como colaborador: *Settings > Collaborators*.

## Passo 2 - Mendeley -> referencias.bib

1. No Mendeley, crie a colecao **Tese** e mantenha nela tudo o que sera citado.
2. Para atualizar: selecionar tudo na colecao > **Export** > **BibTeX (.bib)** > salvar
   por cima de `tex/referencias.bib` > commit (`refs: atualiza bib`).
3. Cite no texto com `\citep{chave}` / `\citet{chave}` usando as chaves exportadas.

> Se a exportacao manual cansar: Zotero + Better BibTeX mantem o `.bib` sincronizado
automaticamente e importa a biblioteca do Mendeley.

## Passo 3 - Editor

**Opcao A - Overleaf** (sync com GitHub exige plano pago):
New Project > Import from GitHub > `tese-viscoelastic`. Main document: `tex/main.tex`.

**Opcao B - Local (VS Code + LaTeX Workshop):**
```
cd tex
latexmk main.tex        # PDF em tex/build/main.pdf
```

## Passo 4 - Claude

- **Projeto "Doutorado" no claude.ai:** em *Project knowledge* > **Add content** > **GitHub** >
  selecione o repositorio e marque `docs/`, `tex/capitulos/` e `AGENTS.md`.
  Use *Sync* depois de commits importantes.
- **Edicao direta (Claude Code):** abra o repositorio; o `CLAUDE.md` carrega as regras e o contexto
  automaticamente.

## Passo 5 - ChatGPT

- Conecte o GitHub em *Settings > Connectors* e autorize somente este repositorio.
- Use para **revisao e segunda opiniao** (somente leitura). Peca sempre: "leia AGENTS.md e
  docs/CONTEXTO.md antes".

## Fluxo de trabalho diario

1. `git pull`
2. Trabalhe (texto, script, simulacao)
3. Rode os scripts que geram figuras alteradas
4. `git add . && git commit -m "cap04: tabela lambda revisada" && git push`
5. Sync no projeto do Claude quando mudar algo estrutural

## Regras de ouro

- Referencia so entra pelo Mendeley.
- Figura so muda pelo script.
- Decisao de metodo vai para `docs/decisoes.md`.
- Resultado ANSYS pesado (`.rst`, `.db`) fica fora do Git; guarde em disco/nuvem e registre o caminho.
