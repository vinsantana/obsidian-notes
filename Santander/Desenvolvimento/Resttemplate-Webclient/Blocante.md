```
return webClient
.get()
.uri(uriBuilder -> uriBuilder.path("/{cep}/json/").build(cep))
.retrieve()
.bodyToMono(String.class)
.block();
```

Para tornar a nossa requisição bloqueante como é no padrão do RestTemplate, feign e jax-rs ... precisamos implementar o **.[[block]]** 🙃