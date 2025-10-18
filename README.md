# Sistema de Reservas de Hotel - Desafio DIO .NET

Este é um projeto desenvolvido como parte do desafio da trilha **.NET - Explorando a linguagem C#** da [DIO](https://www.dio.me/). O sistema simula um hotel onde é possível realizar reservas, cadastrar hóspedes e suítes, calcular valores e aplicar descontos conforme as regras definidas.

## 🎯 Objetivo

Implementar um sistema de hospedagem com as seguintes funcionalidades:
- Cadastro de hóspedes (classe `Pessoa`)
- Cadastro de suítes (classe `Suite`)
- Realização de reservas (classe `Reserva`)
- Validação de capacidade da suíte
- Cálculo de valor da diária com desconto para estadias de 10 dias ou mais

## 📐 Diagrama de Classes

![Diagrama de Classes do Sistema](diagrama_classe_hotel.png)

## 📁 Estrutura do Projeto

```
trilha-net-explorando-desafio/
├── Models/
│   ├── Pessoa.cs        
│   ├── Suite.cs        
│   └── Reserva.cs       
├── .gitignore
├── DesafioProjetoHospedagem.csproj
├── Program.cs         
├── README.md           
└── diagrama_classe_hotel.png 
```

## ✅ Regras Implementadas

1. **Validação de Capacidade**: Não é possível reservar uma suíte com capacidade menor que o número de hóspedes. Caso contrário, uma exceção (`ArgumentException`) é lançada.
2. **Cálculo de Diária**: O valor total é calculado por: `DiasReservados × ValorDiaria`.
3. **Desconto**: Para reservas de 10 dias ou mais, é aplicado um desconto de 10% no valor total.

## 🚀 Como Executar

1. Clone o repositório:
```bash
git clone https://github.com/Maike-Simoncini/trilha-net-explorando-desafio.git
cd trilha-net-explorando-desafio
```

2. Compile e execute o projeto:
```bash
dotnet run
```

> 💡 Certifique-se de ter o [.NET SDK](https://dotnet.microsoft.com/download) instalado em sua máquina.

## 📝 Exemplo de Uso (no Program.cs)

```csharp
// Criar uma suíte
Suite suite = new Suite("Premium", 2, 250.0m);

// Criar hóspedes
List<Pessoa> hospedes = new List<Pessoa>
{
    new Pessoa { Nome = "João", Sobrenome = "Silva" },
    new Pessoa { Nome = "Maria", Sobrenome = "Oliveira" }
};

// Criar reserva
Reserva reserva = new Reserva(12); // 12 dias
reserva.CadastrarSuite(suite);
reserva.CadastrarHospedes(hospedes);

// Mostrar resultados
Console.WriteLine($"Quantidade de hóspedes: {reserva.ObterQuantidadeHospedes()}");
Console.WriteLine($"Valor da diária (com desconto): R$ {reserva.CalcularValorDiaria():F2}");
```

## 📝 Licença

Este projeto é educacional e pode ser usado livremente para fins de aprendizado.
