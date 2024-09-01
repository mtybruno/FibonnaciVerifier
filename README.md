### Fibonnaci Verifier

This code verifies if the users inputed number belongs to the fibonnaci sequence.
At the same time it asks if the user wants to try another number and checks for invalid characteres.

- Made with C#

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;

namespace FibonnaciVerifier
{
    class IsFibonnaci
    {
        static bool IsItFibonacci(int numero)
        {
            int a = 0, b = 1;
            while (b <= numero)
            {
                if (b == numero)
                {
                    return true;
                }
                int temp = a;
                a = b;
                b = temp + b;
            }
            return false;
        }
        static void Main()
        {
            string repeat;
            do
            {
                int numero;
                bool numeroValido;

                do
                {
                    Console.Write("Digite um numero: ");
                    string entrada = Console.ReadLine();
                    numeroValido = int.TryParse(entrada, out numero);

                    if (!numeroValido)
                    {
                        Console.WriteLine("Entrada invalida. digite um numero valido.");
                    }

                } while (!numeroValido);

                if (IsItFibonacci(numero))
                {
                    Console.WriteLine($"O numero {numero} pertence a sequencia de Fibonacci.");
                }
                else
                {
                    Console.WriteLine($"O numero {numero} não pertence a sequencia de Fibonacci.");
                }

                do
                {
                    Console.Write("verificar outro numero? (y/n): ");
                    repeat = Console.ReadLine().ToLower();

                    if (repeat != "y" && repeat != "n")
                    {
                        Console.WriteLine("Opcao invalida. digite 'y' para sim ou 'n' para não.");
                    }

                } while (repeat != "y" && repeat != "n");

            } while (repeat == "y");

            Console.WriteLine("End program.");
        }
    }
}
```
