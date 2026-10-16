# Calculadora de Frete em Java

## Sobre o projeto

Este projeto é uma calculadora de frete desenvolvida em Java, que permite calcular o valor do envio de uma encomenda de acordo com o peso, a distância e a transportadora escolhida pelo usuário.

O programa oferece três opções de transportadoras: **Sedex, Jadlog e Azul**, cada uma com uma fórmula de cálculo própria.

O principal objetivo do projeto é praticar os conceitos de **Programação Orientada a Objetos (POO)**, especialmente o uso de interfaces, classes e polimorfismo.

## Tecnologias utilizadas

- **Java** — linguagem de programação utilizada.
- **Scanner** — para receber os dados digitados pelo usuário.
- **Interface** — para definir um padrão de cálculo de frete.
- **Polimorfismo** — para utilizar diferentes implementações de cálculo por meio de uma mesma interface.

## Funcionalidades

- Solicita o peso da encomenda.
- Solicita a distância do envio.
- Permite escolher entre três transportadoras.
- Calcula o frete conforme a transportadora selecionada.
- Exibe o resultado com duas casas decimais.
- Informa quando uma opção inválida é selecionada.

## Estrutura do projeto

### `Frete`
Recebe uma implementação da interface `CalculadoraFrete` e utiliza o método `calcularFrete()` para realizar o cálculo.

### `CalculadoraFrete`
Interface que define o método `calcular()`, estabelecendo um padrão para as diferentes estratégias de cálculo.

### `CalculadoraFreteSedex`
Calcula o frete multiplicando o peso pela distância.

**Fórmula:** `peso * distancia`

### `CalculadoraFreteJadlog`
Calcula o frete somando o peso à distância.

**Fórmula:** `peso + distancia`

### `CalculadoraFreteAzul`
Calcula o frete elevando o peso ao quadrado e somando a distância.

**Fórmula:** `peso * peso + distancia`

### `Main`
Classe principal responsável por receber os dados do usuário, apresentar o menu de opções, selecionar a estratégia de cálculo e exibir o resultado.

## Como executar

1. Instale o [Java JDK](https://www.oracle.com/java/technologies/downloads/).
2. Salve o código em um arquivo chamado `Main.java`, pois a classe `Main` é a classe pública do código apresentado.
3. Abra o terminal na pasta onde o arquivo foi salvo.
4. Compile o programa:

   ```bash
   javac Main.java
   ```

5. Execute o programa:

   ```bash
   java Main
   ```

## Exemplo de execução

```text
Digite o peso:
2
Digite a distancia:
10
Escolha sua transportadora:
1 - Sedex
2 - Jadlog
3 - Azul
1
Resultados do Frete: 20.00
```

Nesse exemplo, o peso é `2`, a distância é `10` e a transportadora selecionada é o Sedex. O resultado é `2 * 10 = 20`.

## Conceitos de programação aplicados

- **Abstração:** a interface `CalculadoraFrete` define o comportamento esperado para os cálculos.
- **Polimorfismo:** diferentes classes implementam o mesmo método `calcular()` de maneiras distintas.
- **Encapsulamento:** a classe `Frete` mantém sua referência à calculadora como um atributo privado.
- **Injeção de dependência:** a implementação utilizada é recebida pelo construtor da classe `Frete`.
- **Padrão Strategy:** o projeto utiliza diferentes estratégias de cálculo que podem ser selecionadas em tempo de execução.

## Observação

As fórmulas utilizadas são exemplos didáticos para demonstrar diferentes estratégias de cálculo. Elas não representam necessariamente as tarifas reais das transportadoras.

## Autoria

Projeto desenvolvido para praticar Java e conceitos de Programação Orientada a Objetos.
