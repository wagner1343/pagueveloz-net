# pagueveloz-net
Biblioteca .NET (c#) da PagueVeloz

Instanciando o client:

```csharp
var credentials = new PagueVelozCredentials("email", "token");
var client = new PagueVelozClient(PagueVelozEnvironment.Sandbox, credentials); 
```

Emitindo um boleto:

```csharp
var emissao = new EmissaoDTO()
{
    Sacado = "Joãozinho",
    CPFCNPJSacado = "460.844.654-12",
    Valor = 100m,
    Vencimento = DateTime.Today.AddDays(10)
};

var retorno = await client.Boletos.EmitirAsync(emissao);
```

Fazer um request na API:

```csharp
var retorno = await client.GetAsync<string>("api/v1/ping");
```