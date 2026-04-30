# Verificador de Números Primos

## Descrição

Este programa verifica se um número informado pelo usuário é primo ou não.

## Função `e_primo(n)`

A função `e_primo` verifica se um número é primo seguindo a lógica:

- Números menores que 2 não são primos
- 2 é primo (único número par primo)
- Números pares maiores que 2 não são primos
- Para números ímpares, verifica a divisibilidade até a raiz quadrada

### Código

```python
def e_primo(n):
    """Verifica se um número é primo."""
    if n < 2:
        return False
    if n == 2:
        return True
    if n % 2 == 0:
        return False
    
    for i in range(3, int(n ** 0.5) + 1, 2):
        if n % i == 0:
            return False
    return True
```

## Função `main()`

A função principal solicita um número ao usuário e exibe se o número é primo ou não.

### Código

```python
def main():
    """Função principal para testar a função e_primo."""
    numero = int(input("Digite um número para verificar se é primo: "))
    if e_primo(numero):
        print(f"{numero} é um número primo.")
    else:
        print(f"{numero} não é um número primo.")
```

## Como Executar

1. Execute o programa em um interpretador Python
2. Digite um número quando solicitado
3. O programa informará se o número é primo

## Exemplos

| Entrada | Saída |
|---------|-------|
| 2 | 2 é um número primo. |
| 7 | 7 é um número primo. |
| 10 | 10 não é um número primo. |
| 1 | 1 não é um número primo. |

## Complexidade

- **Tempo:** O(n^0.5) - verifica apenas até a raiz quadrada do número
- **Espaço:** O(1) - usa espaço constante