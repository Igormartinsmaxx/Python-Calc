"""Projeto calculadora"""

def somar(a, b):
    return a + b

def subtrair(a, b):
    return a - b

def multiplicar(a, b):
    return a * b

def dividir(a, b):
    if b == 0:
        return "Erro: Divisão por zero não é permitida!"
    return a / b

def calculadora():
    print("=== Calculadora ===")
    print("Escolha a operação:")
    print("1. Soma (+)")
    print("2. Subtração (-)")
    print("3. Multiplicação (*)")
    print("4. Divisão (/)")
    
    while True:
        try:
            escolha = int(input("Digite o número da operação desejada (1/2/3/4): "))
            if escolha not in [1, 2, 3, 4]:
                print("Opção inválida! Tente novamente.")
                continue

            num1 = float(input("Digite o primeiro número: "))
            num2 = float(input("Digite o segundo número: "))

            if escolha == 1:
                print(f"Resultado: {num1} + {num2} = {somar(num1, num2)}")
            elif escolha == 2:
                print(f"Resultado: {num1} - {num2} = {subtrair(num1, num2)}")
            elif escolha == 3:
                print(f"Resultado: {num1} * {num2} = {multiplicar(num1, num2)}")
            elif escolha == 4:
                print(f"Resultado: {num1} / {num2} = {dividir(num1, num2)}")
            
            nova_operacao = input("Deseja realizar outra operação? (s/n): ").lower()
            if nova_operacao != 's':
                print("Encerrando a calculadora. Obrigado!")
                break
        except ValueError:
            print("Erro: Entrada inválida! Digite apenas números.")
        except Exception as e:
            print(f"Ocorreu um erro inesperado: {e}")

if __name__ == "__main__":
    calculadora()
