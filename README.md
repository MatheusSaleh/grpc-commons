# grpc-commons

Contrato gRPC (Protobuf) compartilhado pelos serviços da plataforma de pedidos.
Visão geral, arquitetura e como rodar tudo: **[order-platform](https://github.com/MatheusSaleh/order-platform)**.

![Plataforma em funcionamento](https://raw.githubusercontent.com/MatheusSaleh/order-platform/main/docs/demo.gif)

<sub>Este contrato é usado pelo order-client e pelo order-server na plataforma abaixo.</sub>

## O que tem aqui

- [`src/main/proto/order.proto`](src/main/proto/order.proto): serviço `OrderService` (`PlaceOrder`, `GetOrderStatus`) e mensagens
- Build Maven que gera as classes Java (`br.com.exemplo.grpc`) e publica um `.jar`

## Como usar em outro serviço

```xml
<repositories>
  <repository>
    <id>jitpack.io</id>
    <url>https://jitpack.io</url>
  </repository>
</repositories>

<dependency>
  <groupId>com.github.MatheusSaleh</groupId>
  <artifactId>grpc-commons</artifactId>
  <version>1.0.0</version>
</dependency>
```

## Versionamento

Toda mudança no `.proto` gera uma nova tag (`1.0.0`, `1.1.0`...), e o JitPack compila a tag sob demanda.
Mudanças compatíveis (novos campos com novos números) são *minor*; remover ou renumerar campos é *major*.

Para testar uma mudança localmente antes de criar a tag:

```bash
./mvnw install   # instala no ~/.m2 e os serviços passam a usar a versão local
```
