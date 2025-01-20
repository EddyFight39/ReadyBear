
# ReadyBeer

## Descripción

**BeerCommerce** es una implementación de ejemplo de una plataforma de comercio electrónico basada en arquitectura serverless. Está diseñada para vender cervezas en línea, permitiendo la gestión de usuarios, productos, pedidos, pagos y envíos.

Este proyecto es solo una muestra de cómo se pueden construir microservicios serverless y no es una solución lista para usar. Está diseñado como referencia para aprender a implementar soluciones event-driven y serverless utilizando AWS.

_Por favor, ten en cuenta que al desplegar esta plataforma en tu cuenta de AWS, puedes generar cargos si superas los límites del nivel gratuito. Para monitorear tus costos, te recomendamos usar [AWS Cost Explorer](https://aws.amazon.com/aws-cost-management/aws-cost-explorer/)._

## Arquitectura

### Vista General

Este es un esquema de alto nivel de cómo interactúan los diferentes microservicios que componen la plataforma de BeerCommerce. Cada servicio está diseñado para gestionar una parte del proceso de compra de cerveza.

![Diagrama de flujo](docs/images/flow.png)

### Servicios Backend

| Servicio        | Descripción                               |
|-----------------|-------------------------------------------|
| [usuarios](usuarios/)  | Gestión de usuarios, autenticación y autorización. |
| [cervezas](cervezas/)  | Información sobre las cervezas disponibles para vender. |
| [pedidos](pedidos/)    | Gestión de creación de pedidos y su seguimiento. |
| [inventario](inventario/) | Gestión del inventario de cervezas y estado de existencias. |
| [envio](envio/)        | Gestión de envíos y seguimiento de paquetes. |
| [precios-envio](precios-envio/) | Cálculo de costos de envío para las cervezas. |
| [pagos](pagos/)        | Gestión de cobros y reembolsos. |

### Servicio Frontend

| Servicio       | Descripción                               |
|----------------|-------------------------------------------|
| [api-frontend](api-frontend/) | API para interactuar con los servicios del backend desde la interfaz de usuario. |

### Infraestructura

| Servicio        | Descripción                               |
|-----------------|-------------------------------------------|
| [pipeline](pipeline/) | Pipeline CI/CD para despliegues automáticos. |
| [plataforma](plataforma/) | Recursos fundamentales para desplegar los servicios del backend. |

### Recursos Compartidos

| Nombre       | Descripción                               |
|--------------|-------------------------------------------|
| [docs](docs/) | Documentación sobre cómo usar y contribuir al proyecto. |
| [shared](shared/) | Recursos comunes accesibles para todos los servicios. |

## Tecnologías Utilizadas

- **Comunicación**: 
  - [AWS AppSync](https://aws.amazon.com/appsync/) para la interacción entre usuarios y la plataforma.
  - [Amazon API Gateway](https://aws.amazon.com/api-gateway/) para la comunicación sincrónica entre microservicios.
  - [Amazon EventBridge](https://aws.amazon.com/eventbridge/) para la comunicación asincrónica basada en eventos.

- **Autenticación/Autorización**:
  - [Amazon Cognito](https://aws.amazon.com/cognito/) para la gestión de usuarios y autenticación.
  - [AWS IAM](https://aws.amazon.com/iam/) para la autorización de acceso entre microservicios.

- **Cómputo**:
  - [AWS Lambda](https://aws.amazon.com/lambda/) para ejecutar funciones serverless en respuesta a eventos o solicitudes API.

- **Almacenamiento**:
  - [Amazon DynamoDB](https://aws.amazon.com/dynamodb/) como base de datos NoSQL para almacenar información de productos, pedidos, usuarios, etc.

- **CI/CD**:
  - [AWS CloudFormation](https://aws.amazon.com/cloudformation/) para definir infraestructura como código.
  - [Amazon CodePipeline](https://aws.amazon.com/codepipeline/) para automatizar despliegues.

- **Monitoreo**:
  - [Amazon CloudWatch](https://aws.amazon.com/cloudwatch/) para la recolección de métricas y registros.
  - [AWS X-Ray](https://aws.amazon.com/xray/) para realizar trazabilidad entre los microservicios.

## Documentación

Consulta la [documentación](docs/) para obtener más información sobre cómo empezar, cómo utilizar los servicios y cómo contribuir al proyecto.

## Contribuir

Si deseas contribuir a BeerCommerce, por favor revisa las guías de [contribución](CONTRIBUTING.md) y de [cómo empezar](docs/getting_started.md) para comenzar.

---


