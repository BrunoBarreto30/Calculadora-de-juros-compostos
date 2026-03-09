# Calculadora-de-juros-compostos
Acabei de criar uma ***mini‑calculadora de investimentos em Python*** para mostrar como os juros compostos fazem o seu dinheiro crescer.

def solicitar_numero(mensagem, tipo=float):
   while True:
     try:
        return tipo(input(mensagem + ":").replace(",", "."))
     except ValueError:
       print("Valor inválido. Digite apenas números (ex: 1000 ou 7,5) .")

def main():
    print("Calculadora de Investimentos (Juros Compostos)")
    c = solicitar_numero("Digite o valor inicial do investimento (R$)", float)
    i_percent = solicitar_numero("Digite a taxa anual da rentabilidade (%)", float)
    t = solicitar_numero("Digite o tempo de investimento (em anos)", int)


    i = i_percent / 100.0
    m = c *(1 + i) ** t
    juros = m - c


    print("\nResumo da simulação:")
    print(f"Valor inicial: R${c:,.2f}")
    print(f"Taxa anual: {i_percent:.2f}%")
    print(f"Tempo de investimento: {t} anos(s)")
    print(f"Valor final: R${m:,.2f}")
    print(f"Juros: R${juros:,.2f}")

if __name__ == "__main__":
    main()
