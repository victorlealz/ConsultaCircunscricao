# Localizador de Delegacias PB

Sistema simples para consulta de circunscrição policial e localização de delegacias da Polícia Civil da Paraíba.

## Funcionalidades

- Seleção de município entre os 223 municípios da Paraíba.
- Consulta de bairros por município.
- Busca de delegacias responsáveis pela circunscrição.
- Pesquisa direta por cidade, bairro ou delegacia.
- Consulta de delegacias especializadas.
- Exibição de endereço e telefone.
- Acesso rápido à localização da unidade pelo Google Maps.
- Utilização de dados locais como contingência quando a API estiver indisponível.

## Fonte dos dados

O sistema utiliza a API:

```text
https://api-sgpp-gedes.rke.codataprd.pb.gov.br/api/v1
```

Principais endpoints utilizados:

### Consulta de bairros

```text
GET /consulta/bairros?municipio={id}
```

Exemplo:

```text
https://api-sgpp-gedes.rke.codataprd.pb.gov.br/api/v1/consulta/bairros?municipio=1336
```

### Consulta de delegacias

```text
GET /consulta/lista-delegacias?municipio={municipio}&limit=100
```

Opcionalmente, pode ser informado o bairro:

```text
GET /consulta/lista-delegacias?municipio={municipio}&bairro={bairro}&limit=100
```

## Funcionamento

O sistema tenta consultar os dados diretamente na API.

Caso a API esteja indisponível ou não retorne resultados, algumas consultas utilizam uma base local incorporada ao próprio arquivo HTML (**fallback LOCAL**).

Por isso, os resultados podem ser identificados como:

- **Ao Vivo (PCPB)**: informação obtida diretamente da API.
- **Base local**: informação obtida da base de contingência existente no sistema.

## Tecnologias

O sistema foi desenvolvido utilizando apenas:

- HTML
- CSS
- JavaScript
- Fetch API

Não há necessidade de instalação de bibliotecas ou frameworks.

## Como executar

Basta abrir o arquivo HTML em um navegador moderno.

Também é possível hospedar o arquivo em qualquer servidor web estático.

## Observação

Este é um sistema **não oficial**, desenvolvido como ferramenta de consulta rápida.

As informações oficiais devem ser confirmadas, quando necessário, nos canais da Polícia Civil da Paraíba e no portal Delegacia Online PB.

## Autor

WinZip144
