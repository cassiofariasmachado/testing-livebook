# Testando o livebook

## Executando o livebook com Docker

```powershell
docker run -p 8080:8080 -v ${pwd}:/data --rm livebook/livebook
```

## Executando código

```elixir
Enum.map([0, 1, 2, 3, 4], fn elem -> elem + 1 end)
```

## Criando módulos

```elixir
defmodule HelloWorld do
  def message(), do: "Hello World"
end

HelloWorld.message()
```

## Criando testes

```elixir
ExUnit.start(autorun: false)

defmodule HelloWorldTest do
  use ExUnit.Case, async: true

  test "message" do
    assert "Hello World" == HelloWorld.message()
  end
end

ExUnit.run()
```

## Instalando dependências

```elixir
Mix.install([
  {:tesla, "~> 1.4.0"}
])

{:ok, %Tesla.Env{body: body}} = Tesla.get("https://google.com")

body
```
