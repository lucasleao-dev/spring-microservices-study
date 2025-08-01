

```markdown
# 🎓 Sistema de Gestão Escolar - Microsserviços com Spring Boot

Este projeto é um estudo de arquitetura de microsserviços inspirado em sistemas distribuídos modernos como o da Netflix. Foca em aplicar práticas reais de engenharia de software, com ênfase em escalabilidade, mensageria, autenticação, observabilidade e resiliência.

---

## ✨ Tecnologias Utilizadas

| Categoria           | Tecnologias                                                                 |
|---------------------|------------------------------------------------------------------------------|
| **Frameworks**       | Spring Boot 3.x, Spring Cloud Config, Spring Security, Spring Cloud Gateway |
| **Mensageria**       | Apache Kafka                                                                |
| **Descoberta de Serviços** | Spring Cloud Netflix Eureka                                                |
| **Persistência**     | PostgreSQL, MongoDB (opcional)                                              |
| **Autenticação**     | JWT (JSON Web Token)                                                        |
| **Monitoramento**    | Prometheus, Grafana                                                         |
| **CI/CD e Qualidade**| GitLab CI/CD, SonarQube                                                     |
| **Orquestração**     | Docker, Kubernetes                                                          |

---

## 🔧 Funcionalidades por Serviço

| Serviço               | Responsabilidades                                                                 |
|-----------------------|-----------------------------------------------------------------------------------|
| `user-service`        | Gestão de usuários (Admin, Aluno, Professor) e autenticação via JWT              |
| `student-service`     | Cadastro e consulta de alunos                                                     |
| `course-service`      | Gerenciamento de cursos, disciplinas e professores                                |
| `enrollment-service`  | Matrícula de alunos em disciplinas, controle de pré-requisitos                    |
| `grade-service`       | Lançamento e consulta de notas, geração de boletins                               |
| `notification-service`| Envio de notificações (ex: notas lançadas, matrícula confirmada) via Kafka       |
| `api-gateway`         | Roteamento centralizado e autenticação                                            |
| `config-server`       | Centralização de configurações dos microsserviços                                 |
| `eureka-server`       | Registro e descoberta de serviços                                                 |
| `logging-service`     | Coleta de logs (opcional para observabilidade avançada)                           |

---

## 🧱 Estrutura do Projeto

```

school-system/
├── api-gateway/
├── config-server/
├── eureka-server/
├── user-service/
├── student-service/
├── course-service/
├── enrollment-service/
├── grade-service/
├── notification-service/
├── logging-service/ (opcional)
├── docker-compose.yml
└── README.md

````

---

## 🚀 Como Rodar o Projeto

### ✅ Pré-requisitos

- Java 17+
- Docker e Docker Compose
- Git
- Kafka (já incluso no `docker-compose.yml`)
- PostgreSQL (já incluso)

### 🧪 Subir infraestrutura com Docker

```bash
docker-compose up -d
````

### 🌐 Acessos Padrão

* Eureka Dashboard: `http://localhost:8761`
* Config Server: `http://localhost:8888`
* API Gateway: `http://localhost:8080`
* Kafka UI (se usar): `http://localhost:9000`
* Grafana: `http://localhost:3000` (admin/admin)
* Prometheus: `http://localhost:9090`

---

## 📊 Monitoramento e Observabilidade

* Métricas expostas via Actuator + Prometheus
* Dashboards customizados no Grafana
* Possível integração futura com Zipkin ou Jaeger (tracing distribuído)

---

## 🧪 Testes Automatizados

* JUnit 5 para testes unitários e de integração
* Testcontainers (para simular Kafka e bancos em CI)
* Testes de contrato com Spring Cloud Contract (planejado)

---

## 🧭 Roadmap de Evolução

| Fase                       | Conteúdo                                                         |
| -------------------------- | ---------------------------------------------------------------- |
| **Fase 1 (intermediária)** | Serviços principais, JWT, Kafka, Eureka, Config Server, Docker   |
| **Fase 2 (avançada)**      | Resilience4j, Circuit Breakers, Sagas, observabilidade completa  |
| **Fase 3 (expert)**        | Kubernetes, Helm, deploy automático, testes com contract testing |

---

## 🧠 Inspiração Arquitetural

Este projeto foi fortemente inspirado em arquiteturas de empresas como a **Netflix**, utilizando componentes como:

* Spring Boot + Zuul/API Gateway
* Kafka para eventos
* Eureka para service discovery
* Config Server para configuração centralizada
* Prometheus + Grafana para monitoramento
* Docker e Kubernetes para orquestração
