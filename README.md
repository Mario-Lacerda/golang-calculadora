# Desafio Dio - Criando uma Calculadora com Go



### **projeto completo em Go para criar uma calculadora:**

go

```go
package main

import (
    "fmt"
    "strconv"
)

func main() {
    // Recebe os operandos e o operador do usuário
    fmt.Print("Digite o primeiro operando: ")
    var operando1 float64
    fmt.Scanln(&operando1)

    fmt.Print("Digite o segundo operando: ")
    var operando2 float64
    fmt.Scanln(&operando2)

    fmt.Print("Digite o operador (+, -, *, /): ")
    var operador string
    fmt.Scanln(&operador)

    // Converte os operandos para float64
    operando1Num, err := strconv.ParseFloat(operando1, 64)
    if err != nil {
        fmt.Println("Erro ao converter o primeiro operando para float64:", err)
        return
    }

    operando2Num, err := strconv.ParseFloat(operando2, 64)
    if err != nil {
        fmt.Println("Erro ao converter o segundo operando para float64:", err)
        return
    }

    // Realiza a operação
    var resultado float64
    switch operador {
    case "+":
        resultado = operando1Num + operando2Num
    case "-":
        resultado = operando1Num - operando2Num
    case "*":
        resultado = operando1Num * operando2Num
    case "/":
        if operando2Num == 0 {
            fmt.Println("Não é possível dividir por zero")
            return
        }
        resultado = operando1Num / operando2Num
    default:
        fmt.Println("Operador inválido")
        return
    }

    // Imprime o resultado
    fmt.Printf("Resultado: %.2f\n", resultado)
}
```



#### **Como usar:**

1. Execute o programa `go run main.go`.
2. Digite os operandos e o operador conforme solicitado.
3. O programa imprimirá o resultado da operação.



#### **Exemplo de uso:**

```plaintext
Digite o primeiro operando: 10
Digite o segundo operando: 5
Digite o operador (+, -, *, /): +
Resultado: 15.00
```



