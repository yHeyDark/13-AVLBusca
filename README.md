# Árvores AVL - Busca Recursiva
---

## 🎯 Objetivo da Atividade

Implementar a função de **busca recursiva** em uma árvore AVL completa e funcional.

Nesta atividade, você receberá uma árvore AVL totalmente implementada (com inserção e balanceamento automático). Sua tarefa é implementar apenas a função de busca utilizando **recursão**.

---

## � Busca em Árvore Binária de Busca

A busca em uma árvore binária de busca aproveita a propriedade de ordenação dos elementos para encontrar valores de forma eficiente.

### Princípio da Busca

Em uma ABB, para qualquer nó:
- Todos os valores à **esquerda** são **menores**
- Todos os valores à **direita** são **maiores**

### Algoritmo Recursivo de Busca

**Casos Base:**
1. **Nó é NULL**: O elemento não existe na árvore
2. **Valor encontrado**: O valor do nó atual é igual ao valor procurado

**Casos Recursivos:**
- Se `valor < no->valor`: Buscar na subárvore **esquerda**
- Se `valor > no->valor`: Buscar na subárvore **direita**

**Visualização:**
```
Procurando 15 na árvore:
        20
       /  \
      10   30
     / \   / \
    5  15 25 35

Passo 1: 15 < 20 → vai para esquerda
Passo 2: 15 > 10 → vai para direita
Passo 3: 15 == 15 → ENCONTRADO!
```

### Complexidade
- **Melhor caso**: O(1) - elemento está na raiz
- **Caso médio**: O(log n) - árvore balanceada
- **Pior caso**: O(log n) - em árvore AVL (sempre balanceada)

---

## 💻 Estrutura do Código

### Estrutura do Nó
```cpp
struct NO {
    int valor;      // Dado armazenado
    NO* esq;        // Ponteiro para filho esquerdo
    NO* dir;        // Ponteiro para filho direito
    int altura;     // Altura do nó (para balanceamento)
};
```

### Funções Principais

- `insereArvore()`: Insere um elemento e rebalanceia se necessário (implementada)
- `alturaNo()`: Retorna a altura de um nó (implementada)
- `fatorBalanceamento()`: Calcula o FB de um nó (implementada)
- `girarDireita()`: Rotação à direita (implementada)
- `girarEsquerda()`: Rotação à esquerda (implementada)
- `buscarElementoArvore()`: **[A IMPLEMENTAR]** Busca recursiva de elemento

---

## ✅ Sua Tarefa

### Implementar `buscarElementoArvore()`

**Localização:** Arquivo `AVL.cpp`, função `void buscarElementoArvore(NO* no, int valor)`

**Requisitos:**
- [ ] Implementar busca recursiva seguindo os comentários no código
- [ ] Imprimir "Elemento encontrado!" quando encontrar o valor
- [ ] Imprimir "Elemento NAO encontrado." quando o valor não existir

**Estrutura sugerida:**

```cpp
void buscarElementoArvore(NO* no, int valor) {
    // 1. Caso base: nó é NULL?
    //    → Imprima "Elemento NAO encontrado." e retorne
    
    // 2. Caso base: valor encontrado?
    //    → Imprima "Elemento encontrado!" e retorne
    
    // 3. Caso recursivo: valor é menor que o nó atual?
    //    → Busque na subárvore esquerda
    
    // 4. Caso recursivo: valor é maior que o nó atual?
    //    → Busque na subárvore direita
}
```

**💡 Dicas:**
- Pense nos **casos base** primeiro (quando parar a recursão)
- A função não retorna valor, apenas imprime o resultado
- Teste com valores que existem E que não existem na árvore

---

## 🧪 Como Testar

### 1. Compile o programa
Utilize o Visual Studio 2022 ou superior

### 2. Insira elementos (Opção 3)
Exemplo: 50, 30, 70, 20, 40, 60, 80

### 3. Visualize a árvore (Opção 4)
Observe a estrutura balanceada automaticamente

### 4. Teste sua busca (Opção 5)

**Casos de teste obrigatórios:**

| Teste | Inserir | Buscar | Resultado Esperado |
|-------|---------|--------|-------------------|
| 1 | 50 | 50 | ✅ Encontrado |
| 2 | 50, 30, 70, 20 | 20 | ✅ Encontrado |
| 3 | 50, 30, 70 | 40 | ❌ NÃO encontrado |
| 4 | (árvore vazia) | 10 | ❌ NÃO encontrado |
| 5 | 50, 30, 70, 20, 40 | 15 | ❌ NÃO encontrado |

---

## 🤔 Perguntas para Reflexão

1. Por que a busca recursiva é mais elegante que a iterativa em árvores binárias?
2. O que acontece se você tentar buscar em uma árvore vazia? Seu código trata esse caso?
3. Você consegue implementar a busca de forma iterativa (usando um laço)?

---

**Boa sorte com a implementação! 🚀**
