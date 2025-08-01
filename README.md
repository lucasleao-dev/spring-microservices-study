

## 🎓 Sistema de Gestão Escolar — Microsserviços com Spring Boot

> Este projeto é um estudo sobre arquitetura de microsserviços utilizando Spring Boot e ferramentas modernas. Ele simula um sistema de gestão escolar, abordando autenticação, controle de usuários, matrículas, lançamentos de notas e envio de notificações.

---

### ✅ Funcionalidades

| Serviço                  | Responsabilidade                                                    |
| ------------------------ | ------------------------------------------------------------------- |
| **User Service**         | Gestão de usuários (aluno, professor, admin) e autenticação via JWT |
| **Course Service**       | Cadastro e gerenciamento de cursos e disciplinas                    |
| **Enrollment Service**   | Matrícula de alunos em disciplinas                                  |
| **Grade Service**        | Lançamento e consulta de notas                                      |
| **Notification Service** | Envio de notificações (e-mail, push) em eventos importantes         |
| **API Gateway**          | Roteamento de requisições e autenticação centralizada               |
| **Logging Service**      | Coleta e centralização de logs para análise e rastreabilidade       |

---

### 🛠️ Tecnologias Usadas

* **Spring Boot 3.x**
* **Spring Cloud Netflix Eureka** – Descoberta de serviços
* **Spring Cloud Config** – Configuração centralizada
* **Kafka** – Mensageria e eventos entre serviços
* **Spring Security + JWT** – Autenticação e autorização
* **Spring Data JPA** – Persistência com PostgreSQL
* **Prometheus** – Coleta de métricas
* **Grafana** – Visualização de métricas
* **Docker + Docker Compose** – Containerização
* **Kubernetes (K8s)** – Orquestração de containers (futuramente)
* **GitLab CI/CD** – Integração e entrega contínua
* **SonarQube** – Análise de qualidade de código

---

### 📦 Estrutura dos Microsserviços

```
school-system/
│
├── user-service/             → Autenticação e usuários
├── course-service/           → Cursos e disciplinas
├── enrollment-service/       → Matrículas
├── grade-service/            → Lançamento de notas
├── notification-service/     → Notificações (Kafka listener)
├── logging-service/          → Coleta de logs
├── api-gateway/              → Roteamento + segurança JWT
├── config-server/            → Spring Cloud Config
├── discovery-server/         → Eureka Server
├── docker-compose.yml        → Infraestrutura local
└── README.md
```

---

### ▶️ Como Rodar o Projeto

#### ✅ Pré-requisitos

* **JDK 17+**
* **Docker** e **Docker Compose**
* **Kafka** rodando (via Docker)
* **Banco de dados PostgreSQL** (via Docker)

#### 📌 Passos básicos

```bash
# 1. Clonar o repositório
git clone https://github.com/seu-usuario/school-system.git
cd school-system

# 2. Subir infraestrutura com Docker
docker-compose up -d

# 3. Rodar serviços localmente (via IDE ou Maven)
./mvnw spring-boot:run -pl user-service
```

---

### 📈 Observabilidade

* Métricas expostas via **Actuator + Prometheus**
* Painéis configurados no **Grafana**
* Logs coletados via **Logging Service** com armazenamento centralizado

---

### 🔐 Segurança

* Autenticação com **JWT** gerado pelo `user-service`
* Autorização por **roles**: `ADMIN`, `ALUNO`, `PROFESSOR`
* Proteção das rotas via API Gateway

---

### ✅ TODO (próximas implementações)

* [ ] Testes unitários e de integração com cobertura SonarQube
* [ ] Orquestração com Kubernetes
* [ ] Dashboards de métricas prontos no Grafana
* [ ] Upload de documentos escolares (ex: boletim em PDF)
* [ ] Frontend em Angular/React (opcional)

---
