============================================================
VERIFICADOR DE LEVANTAMENTO
============================================================

OBJETIVO
------------------------------------------------------------

Este programa compara automaticamente dois arquivos DOCX:

1. Arquivo "_MARCADO"
2. Arquivo "_LEVANTAMENTO"

O objetivo é verificar se o levantamento de loops por
personagem está correto em relação ao script marcado.


============================================================
COMO FUNCIONA
============================================================

O programa:

1. Procura automaticamente os arquivos:
   - *_MARCADO.docx
   - *_LEVANTAMENTO.docx

2. Analisa o arquivo MARCADO:
   - identifica loops
   - identifica personagens
   - relaciona quais loops pertencem a cada personagem

3. Analisa o arquivo LEVANTAMENTO:
   - lê os personagens
   - lê os loops informados
   - verifica o total indicado após "//"

4. Compara os dois arquivos.

5. Gera um relatório com:
   - loops faltando
   - loops extras
   - diferenças entre marcado e levantamento
   - totais incorretos


============================================================
REGRAS IMPORTANTES
============================================================

ARQUIVO MARCADO
------------------------------------------------------------

Estrutura esperada:

COLUNA 0:
- LOOP ou PERSONAGEM

COLUNA 1:
- TIMECODE

COLUNA 2:
- FALA

Exemplo:

001
PEDRO
"Fala..."

Os loops podem estar agrupados:

001 - 002 - 003

O programa considera TODOS os loops da célula.


------------------------------------------------------------
ARQUIVO LEVANTAMENTO
------------------------------------------------------------

Estrutura esperada:

COLUNA 0:
- PERSONAGEM

COLUNA 1:
- LOOPS

Exemplo:

PEDRO | 001 - 002 - 003 //3

O número após "//" é tratado como:
- TOTAL DE LOOPS

Esse número NÃO é considerado loop.


============================================================
NORMALIZAÇÕES AUTOMÁTICAS
============================================================

O programa trata automaticamente:

- "LEO (VO)" = "LEO"
- "VOZERIO ALMOÇO" = "VOZERIO"
- "VOZERIO FESTA" = "VOZERIO"

Também ignora:
- diferenças de maiúsculas/minúsculas
- espaços extras


============================================================
COMO USAR
============================================================

1. Coloque os arquivos DOCX na pasta:

entrada/

2. Execute:

main.exe

3. O relatório será gerado em:

saida/


============================================================
RELATÓRIO
============================================================

O relatório mostra apenas divergências.

Exemplos:

[ERRO]
- loops diferentes entre os arquivos

[FALTANDO]
- personagem existe no marcado
- mas não existe no levantamento

[EXTRA]
- personagem existe no levantamento
- mas não existe no marcado


============================================================
OBSERVAÇÕES
============================================================

- Os loops devem possuir 3 dígitos:
  Exemplo:
  001
  045
  127

- O nome dos arquivos pode variar.

Apenas os sufixos são obrigatórios:
- _MARCADO
- _LEVANTAMENTO


============================================================
FIM
============================================================
