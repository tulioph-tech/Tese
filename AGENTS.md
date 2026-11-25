# Instrucoes para assistentes de IA (Claude, ChatGPT/Codex e outros)

Leia `docs/CONTEXTO.md` antes de qualquer tarefa. Consulte `docs/decisoes.md` antes de propor mudancas de metodo.

## Regras
1. **Referencias:** cite apenas chaves que existam em `tex/referencias.bib`. Nunca invente uma referencia.
   Se faltar fonte, escreva `% TODO: referencia para ...` e avise.
2. **Nao edite** `tex/referencias.bib` (ele e gerado pelo Mendeley).
3. **Notacao:** use as macros de `tex/preambulo.tex` (`\Gs`, `\Gp`, `\etaf`, `\Kd`...). Nao crie simbolos novos sem registrar em `CONTEXTO.md`.
4. **Texto da tese** em portugues (norma culta, voz impessoal). Comentarios de codigo em ASCII, sem acentos.
5. **MATLAB:** compativel com R2014b e Octave; funcoes locais no fim do arquivo; graficos em preto e branco;
   figuras exportadas para `figuras/` em PDF.
6. **Figuras** nunca sao editadas a mao: altere o script que as gera.
7. **Dados brutos** (`dados/brutos/`) sao somente leitura.
8. Commits pequenos, com mensagem em portugues no formato `cap03: descreve calibracao lambda`.
9. Numeros de resultados no texto devem vir de script ou tabela do repositorio, nunca de memoria.
