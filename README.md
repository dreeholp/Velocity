# Velocity Xbox 360 — Entrega de Modificações

## O que foi feito

### ✅ 1. Importação de múltiplos arquivos (Inject Here)
O arquivo `packageviewer.cpp` foi modificado para permitir selecionar vários arquivos de uma vez ao usar a opção **Inject Here**.

**Antes:** abria um arquivo por vez  
**Agora:** abre um seletor com suporte a múltipla seleção (Ctrl+clique ou Shift+clique)

Comportamento novo:
- Cada arquivo é injetado individualmente no pacote
- Se algum arquivo falhar, aparece um aviso listando quais falharam — sem cancelar os demais
- A barra de status exibe quantos arquivos foram injetados com sucesso

---

### ✅ 2. Strings exportadas para tradução
O arquivo `velocity_strings_para_traducao.txt` contém **949 strings** extraídas de todo o código-fonte e dos arquivos de interface (`.cpp` e `.ui`).

---

## Como aplicar as modificações

### Pré-requisitos
- Qt Creator instalado
- Projeto Velocity aberto (clone de https://github.com/gualdimar/velocity)

### Passo a passo

**1. Substituir o arquivo modificado**
```
Copie:  packageviewer.cpp
Para:   Velocity/packageviewer.cpp
        (substitua o arquivo original)
```

**2. Compilar**
- Abra o projeto no Qt Creator
- Menu → Build → Build Project "Velocity"
- Aguarde a compilação sem erros

**3. Testar a multi-importação**
1. Abra um pacote `.stfs` no Velocity
2. Clique com botão direito na árvore de arquivos
3. Selecione **Inject Here**
4. No seletor de arquivos, use **Ctrl+clique** para selecionar vários arquivos
5. Confirme — todos os arquivos devem aparecer na árvore

---

## Como usar o arquivo de tradução

O arquivo `velocity_strings_para_traducao.txt` segue este formato:

```
CHAVE=Texto em inglês
```

**Regras:**
- Traduza apenas o lado **direito** do `=`
- **Não altere** as chaves (lado esquerdo)
- Não remova linhas que começam com `#` (são comentários)

**Exemplo:**
```
# Original:
packageviewer_0001=File injected successfully

# Traduzido:
packageviewer_0001=Arquivo injetado com sucesso
```

Após traduzir, devolva o arquivo `.txt` para implementação do carregamento dinâmico no programa.

---

## Arquivos entregues

| Arquivo | Descrição |
|---|---|
| `packageviewer.cpp` | Arquivo C++ modificado com multi-importação |
| `velocity_strings_para_traducao.txt` | 949 strings para tradução ao português |
| `README.md` | Este documento de instruções |

---

*Modificações realizadas sobre o projeto original disponível em github.com/gualdimar/velocity*
