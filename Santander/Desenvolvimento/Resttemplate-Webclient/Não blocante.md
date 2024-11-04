Reativa

Para tornar nossa request reativa precisamos chamar o "[[subscribe]]" e com isso conseguimos implementar a nossa logica para manipular a resposta obtida mesmo depois depois do fim da execução do método onde a chamada foi implementada.

```
webClient
.get()
.uri(uriBuilder -> uriBuilder.path("/{cep}/json/").build(cep))
.retrieve()
.bodyToMono(String.class)
.subscribe(i -> {
    System.out.println("A request retornou agora ;) ");
});

//logica...
return "ok";
```