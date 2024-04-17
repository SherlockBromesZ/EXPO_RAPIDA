# expoRapida: Exponenciação Modular em Ação 🚀

## O que é isso? 🤔
**expoRapida** é uma função que calcula a exponenciação modular de forma eficiente. Em termos mais simples, ela eleva um número a uma potência bem grande e depois calcula o resto da divisão por um módulo. É como uma calculadora turbinada para matemáticos preguiçosos! 😴

## Para que serve? 🤨
Essa função é útil em várias áreas, como:
- **Criptografia**: Algoritmos como o RSA usam exponenciação modular para garantir a segurança de chaves públicas e privadas. 🔐
- **Teoria dos Números**: O módulo ajuda a estudar as propriedades dos números inteiros e suas relações, como no Pequeno Teorema de Fermat. 🧮
- **Problemas de Programação**: Em competições como a OBI, a exponenciação modular aparece em desafios que exigem soluções eficientes para problemas matemáticos. 🧠

## Como funciona? ⚙️
A mágica por trás da **expoRapida** é a exponenciação binária. Em vez de multiplicar a base por ela mesma várias vezes, o algoritmo utiliza os bits do expoente para acelerar o processo.

### Aqui está um passo a passo:
#### Inicialização:
- O resultado é definido como 1.
- A base é calculada o módulo dela mesma para garantir que esteja dentro do intervalo do módulo.

#### Loop principal:
- Enquanto o expoente for maior que 0:
  - **Verificação de bit**: Se o último bit do expoente for 1 (ou seja, se o expoente for ímpar), o resultado é multiplicado pela base (módulo o módulo).
  - **Deslocamento de bits**: O expoente é deslocado um bit para a direita, o que equivale a dividir por 2 (ignorando o resto).
  - **Quadrado da base**: A base é elevada ao quadrado (módulo o módulo).

#### Retorno:
- A função retorna o resultado final, que é a base elevada ao expoente original, módulo o módulo.

## A Função 🛠️
Aqui está a função completa com o módulo:

```c++
long long expoRapida(long long base, long long expoente, long long modulo) {
    long long resultado = 1;
    base = base % modulo;
    while (expoente > 0) {
        if (expoente & 1)
            resultado = (resultado * base) % modulo;
        expoente = expoente >> 1;
        base = (base * base) % modulo;
    }
    return resultado;
}
```
*Use code with caution.*

## Sem o Módulo 🤔
E aqui está a versão simplificada, sem o módulo:

```c++
long long expoSimples(long long base, long long expoente) {
    long long resultado = 1;
    while (expoente > 0) {
        if (expoente & 1)
            resultado = resultado * base;
        expoente = expoente >> 1;
        base = base * base;
    }
    return resultado;
}
```
*Use code with caution.*

## Truques Bit a Bit 🧙‍♀️
- **& (E bit a bit)**: Usado para verificar se o último bit do expoente é 1, o que indica se o expoente é par ou ímpar.
- **>> (Deslocamento de bits para a direita)**: Usado para dividir o expoente por 2, efetivamente iterando pelos bits do expoente.

## Conclusão 🎉
A **expoRapida** é uma ferramenta poderosa para calcular exponenciação modular, com aplicações em diversas áreas. Compreender como ela funciona e os truques bit a bit envolvidos pode ser útil para resolver problemas de programação e entender conceitos matemáticos.
