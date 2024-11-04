```
private ExchangeFilterFunction logRequest() {
    return ExchangeFilterFunction.ofRequestProcessor(cRequest -> {
        log.info("Request {} {}", cRequest.method(), cRequest.url());
        return Mono.just(cRequest);
    });
}

private ExchangeFilterFunction logResponse() {
    return ExchangeFilterFunction.ofResponseProcessor(cResponse -> {
        log.info("Response status code {} ", cResponse.statusCode());
        return Mono.just(cResponse);
    });
}
```
Métodos criados, agora só implementar eles no **filter** do nosso WebClient.
```
WebClient
.builder()
.baseUrl("https://viacep.com.br/ws/")
.filter(ExchangeFilterFunction.ofResponseProcessor(this::exchangeFilterResponseProcessor))
.filter(logRequest())
.filter(logResponse())
.build();
```