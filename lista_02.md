# Questões objetivas

**1)** Considere o seguinte código JavaScript:

```javascript
//EX01
let p = 10;
let q = 3;
let r = 6;

let resultado = (p % q === 1) && (r * 2 > p) || (q + r < p);
console.log(resultado);

const valores = [3, 6, 9, 12, 15];
let produto = 1;

for (let j = 0; j < valores.length; j++) {
  produto *= valores[j];
}

console.log("O produto dos valores é:", produto);


```
Qual das seguintes alternativas melhor descreve o que o código faz?

A) O código avalia a expressão booleana, imprime `true`, calcula o produto dos números na lista e imprime o resultado no console.

A expressão (p % q === 1) && (r * 2 > p) || (q + r < p) resulta em true (10 % 3 = 1, 6 * 2 > 10, 3 + 6 < 10), impressa no console. O laço for multiplica os valores [3, 6, 9, 12, 15], dando 29.160, exibido como "O produto dos valores é: 29160". A alternativa A descreve isso corretamente.

______

**2)** O código a seguir contém duas funções que calculam o limite de crédito de um cliente com base nos seus gastos e na renda mensal.

```javascript
// Versão 1 da função de análise de crédito
function analisarCredito1() {
    var compras = [2500, 1200, 800, 100];
    var totalCompras = compras[0];
    var limite = 5000;
    var status = 'aprovado';
    var saldoDisponivel = 0;
    var i = 1;

    do {
        totalCompras += compras[i];
        i++;
    } while (limite >= totalCompras && i < compras.length);

    saldoDisponivel = limite - totalCompras;

    if (saldoDisponivel < 0) {
        status = 'negado';
    }
    console.log(`Seu crédito foi ${status}. Saldo disponível: ${saldoDisponivel}.`);
}
```

```javascript
// Versão 2 da função de análise de crédito
function analisarCredito2() {
    var compras = [2500, 1200, 800, 100];
    var totalCompras = compras[0];
    var limite = 5000;
    var status = 'aprovado';
    var saldoDisponivel = 0;
    var i = 1;

    while (limite >= totalCompras && i < compras.length) {
        totalCompras += compras[i];
        i++;
    }

    saldoDisponivel = limite - totalCompras;

    if (saldoDisponivel < 0) {
        status = 'negado';
    }
    console.log(`Seu crédito foi ${status}. Saldo disponível: ${saldoDisponivel}.`);
}
```
Se ambas as funções forem executadas com os valores fornecidos, qual será a saída exibida no console?

A) Ambas as funções exibirão: 'Seu crédito foi aprovado. Saldo disponível: 400.'

Ambas as funções somam as compras [2500, 1200, 800, 100] até 4600, subtraem do limite 5000, resultando em saldo 400, e definem status como 'aprovado' pois 400 >= 0. A saída é "Seu crédito foi aprovado. Saldo disponível: 400." em ambas, pois doWhile e while têm lógica idêntica. A alternativa A está correta.


______

**3)** Considere o seguinte trecho de código em JavaScript:
```javascript
//EX03
const idade = 21;

if (idade >= 18 && idade < 60) {
  console.log("Você é um adulto!");
} else if (idade < 18) {
  console.log("Você é menor de idade!");
} else {
  console.log("Você está na melhor idade!");
}
```
Qual das seguintes alternativas melhor descreve o comportamento do código?

B) O código verifica se a idade pertence à faixa adulta. Se for, exibe "Você é um adulto!". Caso contrário, verifica se é menor de idade e exibe "Você é menor de idade!". Se nenhuma das condições anteriores for verdadeira, exibe "Você está na melhor idade!".

Com idade = 21, o código testa se 18 <= 21 < 60 (verdadeiro), exibindo "Você é um adulto!". A lógica segue: faixa adulta (18-59), menor de idade (< 18), ou melhor idade (>= 60). A alternativa B descreve isso perfeitamente e é a correta.

______

**4)** Qual será o resultado impresso no console após a execução do seguinte código?
```javascript
//EX04
var energiaDisponivel = 1200;
var bateriaExtra = 400;
var consumoDispositivos = [300, 600, 500, 200, 400];

for (var i = 0; i < consumoDispositivos.length; i++) {
    var consumo = consumoDispositivos[i];

    if (consumo <= energiaDisponivel) {
        console.log("Dispositivo " + (i+1) + " ligado. Energia restante: " + (energiaDisponivel - consumo));
        energiaDisponivel -= consumo;
    } else if (consumo <= energiaDisponivel + bateriaExtra) {
        console.log("Dispositivo " + (i+1) + " ligado com bateria extra. Energia restante: " + ((energiaDisponivel + bateriaExtra) - consumo));
        energiaDisponivel = 0;
        bateriaExtra -= (consumo - energiaDisponivel);
    } else {
        console.log("Dispositivo " + (i+1) + " não pode ser ligado. Energia insuficiente.");
    }
}
```

Escolha a opção que responde corretamente:

D)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado. Energia restante: 300

Dispositivo 3 ligado com bateria extra. Energia restante: 200

Dispositivo 4 não pode ser ligado. Energia insuficiente.

Dispositivo 5 não pode ser ligado. Energia insuficiente.

O código usa energiaDisponivel = 1200 e bateriaExtra = 400 para ligar dispositivos [300, 600, 500, 200, 400], imprimindo: "Dispositivo 1 ligado. Energia restante: 900", "Dispositivo 2 ligado. Energia restante: 300", "Dispositivo 3 ligado com bateria extra. Energia restante: 200", "Dispositivo 4 ligado com bateria extra. Energia restante: 0", "Dispositivo 5 não pode ser ligado. Energia insuficiente.". Nenhuma opção está totalmente correta; D erra ao omitir o Dispositivo 4 sendo ligado.

______

**5)** Qual é a principal função do método update() em um jogo desenvolvido com Phaser.js?

Escolha a opção que melhor descreve seu propósito:

B) O método update() é chamado continuamente a cada quadro (frame) do jogo, sendo usado para atualizar a lógica, movimentação e interações dos objetos na cena.

O método update() no Phaser.js é executado a cada frame (ex.: 60 vezes por segundo), atualizando a lógica, movimentação e interações dos objetos do jogo. É essencial para manter a dinâmica em tempo real. A alternativa B descreve isso com precisão e é a correta.

______

**6)** Qual é o principal objetivo do módulo Matter.js Physics em Phaser.js?

Escolha a opção que responde corretamente:

A) Simular física avançada, incluindo corpos rígidos, colisões complexas e interação entre objetos com gravidade e forças.

O módulo Matter.js Physics no Phaser.js simula física avançada, como colisões de corpos rígidos, gravidade e forças, para criar interações realistas em jogos. Ele vai além de física simples, oferecendo dinamismo complexo. A alternativa A está correta por capturar esse objetivo.
______

# Questões dissertativas

**7)** Uma loja online deseja implementar um sistema de classificação de pedidos com base no valor total da compra. O sistema deve determinar a categoria de um pedido com as seguintes regras:

```

Pedidos abaixo de R$50,00 → "Frete não disponível!"

Pedidos entre R$50,00 e R$199,99 (inclusive) → "Frete com custo adicional!"

Pedidos de R$200,00 ou mais → "Frete grátis!"
```
Implemente um pseudocódigo que receba o valor total da compra e exiba a classificação correta do frete para o cliente.

INÍCIO
    // Declarar a variável para o valor total da compra
    REAL valorCompra

    // Solicitar o valor total da compra ao usuário
    ESCREVER "Digite o valor total da compra (em R$): "
    LER valorCompra

    // Verificar as condições e determinar a classificação do frete
    SE valorCompra < 50.00 ENTÃO
        ESCREVER "Frete não disponível!"
    SENÃO SE (valorCompra >= 50.00 E valorCompra <= 199.99) ENTÃO
        ESCREVER "Frete com custo adicional!"
    SENÃO
        ESCREVER "Frete grátis!"
    FIM-SE

FIM

Entrada: O pseudocódigo começa solicitando o valorCompra, que representa o valor total da compra em reais.

Condições:
SE valorCompra < 50.00: Para valores abaixo de R$50,00, exibe "Frete não disponível!".
SENÃO SE (valorCompra >= 50.00 E valorCompra <= 199.99): Para valores entre R$50,00 e R$199,99 (inclusive), exibe "Frete com custo adicional!".
SENÃO: Para valores de R$200,00 ou mais, exibe "Frete grátis!".

Saída: O programa exibe a mensagem correspondente à faixa de valor.
______

**8)** Considere a implementação da classe base Veiculo em um sistema de modelagem de veículos. Sua tarefa é implementar, utilizando pseudocódigo, as classes derivadas Carro e Moto, que herdam da classe Veiculo, adicionando atributos específicos e métodos para calcular o consumo de combustível de um carro e de uma moto, respectivamente.

```
Classe Veiculo:
Atributos:

modelo
ano
Método Construtor(modelo, ano):

Define os valores dos atributos modelo e ano com os valores passados como parâmetro.
Método CalcularConsumo():
```
Implementação genérica para cálculo de consumo, a ser sobrescrita pelas subclasses.
Agora, implemente as classes Carro e Moto, garantindo que ambas herdem de Veiculo e possuam métodos específicos para calcular o consumo de combustível com base na quilometragem e eficiência do veículo.

CLASSE Veiculo
    // Atributos
    STRING modelo
    INTEIRO ano

    // Construtor
    CONSTRUTOR Veiculo(STRING modeloParam, INTEIRO anoParam)
        modelo ← modeloParam
        ano ← anoParam
    FIM-CONSTRUTOR

    // Método genérico para calcular consumo (a ser sobrescrito)
    MÉTODO CalcularConsumo()
        ESCREVER "Método genérico de cálculo de consumo. Sobrescreva nas subclasses."
        RETORNAR 0
    FIM-MÉTODO
FIM-CLASSE

CLASSE Carro HERDA Veiculo
    // Atributos específicos
    REAL eficienciaCombustivel  // km por litro (ex.: 12.5 km/L)
    REAL quilometragem         // km percorridos

    // Construtor
    CONSTRUTOR Carro(STRING modeloParam, INTEIRO anoParam, REAL eficienciaParam, REAL kmParam)
        // Chama o construtor da classe base
        CHAMAR Veiculo(modeloParam, anoParam)
        eficienciaCombustivel ← eficienciaParam
        quilometragem ← kmParam
    FIM-CONSTRUTOR

    // Sobrescrita do método para calcular consumo
    MÉTODO CalcularConsumo()
        REAL consumo
        consumo ← quilometragem / eficienciaCombustivel  // Consumo em litros
        RETORNAR consumo
    FIM-MÉTODO
FIM-CLASSE

CLASSE Moto HERDA Veiculo
    // Atributos específicos
    REAL eficienciaCombustivel  // km por litro (ex.: 25.0 km/L)
    REAL quilometragem         // km percorridos

    // Construtor
    CONSTRUTOR Moto(STRING modeloParam, INTEIRO anoParam, REAL eficienciaParam, REAL kmParam)
        // Chama o construtor da classe base
        CHAMAR Veiculo(modeloParam, anoParam)
        eficienciaCombustivel ← eficienciaParam
        quilometragem ← kmParam
    FIM-CONSTRUTOR

    // Sobrescrita do método para calcular consumo
    MÉTODO CalcularConsumo()
        REAL consumo
        consumo ← quilometragem / eficienciaCombustivel  // Consumo em litros
        RETORNAR consumo
    FIM-MÉTODO
FIM-CLASSE

INÍCIO
    // Criar um carro
    Carro meuCarro ← NOVO Carro("Fusca", 1980, 12.5, 250.0)
    REAL consumoCarro ← meuCarro.CalcularConsumo()
    ESCREVER "Consumo do carro: " + consumoCarro + " litros"

    // Criar uma moto
    Moto minhaMoto ← NOVO Moto("CG 125", 2020, 25.0, 100.0)
    REAL consumoMoto ← minhaMoto.CalcularConsumo()
    ESCREVER "Consumo da moto: " + consumoMoto + " litros"
FIM

Classe Base Veiculo:
Contém os atributos modelo (string) e ano (inteiro), definidos pelo construtor.
O método CalcularConsumo() é genérico e retorna 0, servindo como placeholder para ser sobrescrito.

Classe Carro:
Herda de Veiculo e adiciona eficienciaCombustivel (km/L) e quilometragem (km).
O construtor inicializa os atributos da classe base e os específicos.
CalcularConsumo() calcula o consumo dividindo a quilometragem pela eficiência (ex.: 250 km / 12.5 km/L = 20 litros).

Classe Moto:
Similar a Carro, herda de Veiculo e usa os mesmos atributos adicionais.
O cálculo de consumo segue a mesma lógica, mas a eficiência geralmente é maior em motos (ex.: 100 km / 25 km/L = 4 litros).
______

**9)** Você é um cientista da NASA e está ajudando no desenvolvimento de um sistema de pouso para sondas espaciais em Marte. Seu objetivo é calcular o tempo necessário para que a sonda reduza sua velocidade até um nível seguro para pouso, considerando uma velocidade inicial de entrada na atmosfera marciana e uma taxa de desaceleração constante causada pelo atrito atmosférico e retrofoguetes.

Entretanto, a sonda não pode ultrapassar um tempo máximo de descida para evitar desvios orbitais, nem pode desacelerar além de um limite mínimo, pois isso poderia causar instabilidade no pouso.

Implemente a lógica dessa simulação em pseudocódigo, considerando a seguinte equação para atualização da velocidade:

Considere a fórumla de atualização velocidade:
```
    velocidade = velocidadeInicial - desaceleracao * tempo
```
Seu programa deve determinar quanto tempo será necessário para que a sonda atinja uma velocidade segura de pouso, sem ultrapassar os limites estabelecidos.

INÍCIO
    // Declarar variáveis
    REAL velocidadeInicial
    REAL velocidadeSegura
    REAL desaceleracao
    REAL tempoMaximo
    REAL desaceleracaoMinima
    REAL tempo

    // Definir valores iniciais (exemplo baseado em Marte)
    velocidadeInicial ← 6000.0    // Velocidade de entrada (m/s)
    velocidadeSegura ← 2.0        // Velocidade segura para pouso (m/s)
    desaceleracao ← 50.0          // Desaceleração inicial (m/s²)
    tempoMaximo ← 120.0           // Tempo máximo de descida (s)
    desaceleracaoMinima ← 20.0    // Desaceleração mínima permitida (m/s²)

    // Verificar se a desaceleração está dentro do limite mínimo
    SE desaceleracao < desaceleracaoMinima ENTÃO
        ESCREVER "Erro: Desaceleração abaixo do limite mínimo! Ajustando para o mínimo."
        desaceleracao ← desaceleracaoMinima
    FIM-SE

    // Calcular o tempo necessário para atingir a velocidade segura
    tempo ← (velocidadeInicial - velocidadeSegura) / desaceleracao

    // Verificar se o tempo calculado é viável
    SE tempo <= 0 ENTÃO
        ESCREVER "Erro: Tempo calculado inválido! Verifique os parâmetros."
    SENÃO SE tempo > tempoMaximo ENTÃO
        ESCREVER "Erro: Tempo de descida excede o limite máximo! Pouso inviável."
        ESCREVER "Tempo necessário: " + tempo + " segundos"
    SENÃO
        ESCREVER "Pouso bem-sucedido!"
        ESCREVER "Tempo de descida: " + tempo + " segundos"
        ESCREVER "Velocidade final: " + velocidadeSegura + " m/s"
    FIM-SE

FIM

Entradas:
velocidadeInicial = 6000 m/s: Velocidade típica de entrada na atmosfera marciana.
velocidadeSegura = 2 m/s: Velocidade baixa o suficiente para pouso seguro.
desaceleracao = 50 m/s²: Taxa de desaceleração (atrito + retrofoguetes).
tempoMaximo = 120 s: Limite para evitar desvios orbitais.
desaceleracaoMinima = 20 m/s²: Limite para estabilidade.

Verificação da Desaceleração:
Se desaceleracao for menor que desaceleracaoMinima, ajusta para o valor mínimo e avisa o usuário.

Cálculo do Tempo:
Usa a fórmula: tempo = (velocidadeInicial - velocidadeSegura) / desaceleracao.

Exemplo: (6000 - 2) / 50 ≈ 119.96 segundos.

Validação:
Se tempo <= 0: Indica erro nos parâmetros (ex.: velocidade inicial menor que a segura).
Se tempo > tempoMaximo: O pouso é inviável, e o tempo é exibido para análise.
Caso contrário: O pouso é bem-sucedido, e os detalhes são exibidos.
______

**10)** Em um sistema de análise financeira, as operações de investimento de uma empresa podem ser representadas por matrizes, onde cada linha representa um tipo de investimento e cada coluna representa um período de tempo.

A seguir, é fornecida a implementação da função SomarMatrizesInvestimento(matrizA, matrizB), que soma os valores de duas matrizes de investimento. Sua tarefa é implementar uma função semelhante, porém que realize a multiplicação das matrizes de investimento, determinando como os investimentos afetam os resultados ao longo do tempo.

```
Função SomarMatrizesInvestimento(matrizA, matrizB):  
    # Verifica se as matrizes têm o mesmo número de linhas e colunas  
    Se tamanho(matrizA) ≠ tamanho(matrizB) então:  
        Retornar "As matrizes não podem ser somadas. Elas têm dimensões diferentes."  
    Senão:  
        linhas <- tamanho(matrizA)  
        colunas <- tamanho(matrizA[0])  
        matrizResultado <- novaMatriz(linhas, colunas)  

        # Loop para percorrer cada elemento das matrizes e calcular a soma  
        Para i de 0 até linhas-1 faça:  
            Para j de 0 até colunas-1 faça:  
                matrizResultado[i][j] <- matrizA[i][j] + matrizB[i][j]  

        Retornar matrizResultado  

# Exemplo de uso da função  
investimentosAno1 <- [[1000, 2000], [1500, 2500]]  
investimentosAno2 <- [[1200, 1800], [1300, 2700]]  

totalInvestimentos <- SomarMatrizesInvestimento(investimentosAno1, investimentosAno2)  
Escrever("Total de investimentos acumulados:")  
ImprimirMatriz(totalInvestimentos)  
```
Agora, implemente a função MultiplicarMatrizesInvestimento(matrizA, matrizB), que multiplica as duas matrizes, simulando o efeito de diferentes fatores de crescimento e impacto financeiro nos investimentos ao longo do tempo.

FUNÇÃO MultiplicarMatrizesInvestimento(matrizA, matrizB)
    // Verificar se as matrizes podem ser multiplicadas
    INTEIRO linhasA ← tamanho(matrizA)          // Número de linhas de matrizA
    INTEIRO colunasA ← tamanho(matrizA[0])      // Número de colunas de matrizA
    INTEIRO linhasB ← tamanho(matrizB)          // Número de linhas de matrizB
    INTEIRO colunasB ← tamanho(matrizB[0])      // Número de colunas de matrizB

    SE colunasA ≠ linhasB ENTÃO
        RETORNAR "As matrizes não podem ser multiplicadas. Dimensões incompatíveis."
    SENÃO
        // Criar matriz resultado com dimensões linhasA x colunasB
        matrizResultado ← novaMatriz(linhasA, colunasB)

        // Loop para calcular cada elemento da matriz resultado
        PARA i DE 0 ATÉ linhasA-1 FAÇA
            PARA j DE 0 ATÉ colunasB-1 FAÇA
                REAL soma ← 0
                PARA k DE 0 ATÉ colunasA-1 FAÇA
                    soma ← soma + (matrizA[i][k] * matrizB[k][j])
                FIM-PARA
                matrizResultado[i][j] ← soma
            FIM-PARA
        FIM-PARA

        RETORNAR matrizResultado
    FIM-SE
FIM-FUNÇÃO

// Exemplo de uso da função
INÍCIO
    // MatrizA: Investimentos por tipo e período (2 tipos, 2 períodos)
    investimentos ← [[1000, 2000], [1500, 2500]]

    // MatrizB: Fatores de crescimento por período (2 períodos, 2 novos períodos)
    fatoresCrescimento ← [[1.1, 0.9], [1.2, 1.0]]

    // Multiplicar as matrizes
    resultado ← MultiplicarMatrizesInvestimento(investimentos, fatoresCrescimento)

    // Exibir resultado
    ESCREVER "Resultado dos investimentos ajustados por fatores de crescimento:"
    ImprimirMatriz(resultado)
FIM

Verificação de Compatibilidade:
A multiplicação só é possível se o número de colunas de matrizA (colunasA) for igual ao número de linhas de matrizB (linhasB). Caso contrário, retorna uma mensagem de erro.

Dimensões da Matriz Resultante:
A matriz resultado terá linhasA linhas e colunasB colunas.

Cálculo da Multiplicação:
Para cada elemento matrizResultado[i][j], percorre-se a linha i de matrizA e a coluna j de matrizB, somando os produtos dos elementos correspondentes.

Exemplo com os valores fornecidos:
matrizA = [[1000, 2000], [1500, 2500]] (2x2).
matrizB = [[1.1, 0.9], [1.2, 1.0]] (2x2).

Resultado será uma matriz 2x2:
resultado[0][0] = (1000 * 1.1) + (2000 * 1.2) = 1100 + 2400 = 3500.
resultado[0][1] = (1000 * 0.9) + (2000 * 1.0) = 900 + 2000 = 2900.
resultado[1][0] = (1500 * 1.1) + (2500 * 1.2) = 1650 + 3000 = 4650.
resultado[1][1] = (1500 * 0.9) + (2500 * 1.0) = 1350 + 2500 = 3850.
