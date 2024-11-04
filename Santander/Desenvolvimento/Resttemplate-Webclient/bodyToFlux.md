em como resposta um fluxo de partes de resposta.

```
Flux<CepDTO> flux = consultaCep
                .get()
                .uri(uriBuilder -> uriBuilder.path("/{cep}/json/").build(cep))
                .exchangeToFlux(response -> {
                    if (response.statusCode().equals(HttpStatus.OK)) {
                        return response.bodyToFlux(CepDTO.class);
                    } else {
                        return response.createException().flatMapMany(Mono::error);
                    }
                });
```