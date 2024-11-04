a resposta esperada é única

```
Mono<CepDTO> flux = consultaCep
                .get()
                .uri(uriBuilder -> uriBuilder.path("/{cep}/json/").build(cep))
                .retrieve()
                .bodyToMono(CepDTO.class)
                .block();
``````
Mono<List<CepDTO>> fluxToMonoCollection = consultaCep
                .get()
                .uri(uriBuilder -> uriBuilder.path("/{cep}/json/").build(cep))
                .retrieve()
                .bodyToFlux(CepDTO.class)
                .collectList();
```


```
private Mono<ClientResponse> exchangeFilterResponseProcessor(ClientResponse response) {
        HttpStatus status = response.statusCode();
        if (HttpStatus.INTERNAL_SERVER_ERROR.equals(status)) {
            return response
            .bodyToMono(String.class)
            .flatMap(body -> Mono.error(new RuntimeException(body)));
        }
        return Mono.just(response);
    }
```
Agora que temos o nosso método criado, vamos passar para o filter, chamamos o ExchangeFilterFunction.ofResponseProcessor e passamos o nosso método para dentro e setamos no filter.

```
WebClient
.builder()
.baseUrl("https://blog.sassine.dev")
.filter(ExchangeFilterFunction.ofResponseProcessor(this::exchangeFilterResponseProcessor))
.build();
```