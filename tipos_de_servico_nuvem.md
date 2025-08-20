# 📘 Entendendo o Desafio — Conteúdo de Aula (IaaS/PaaS/SaaS na Azure & Responsabilidade Compartilhada)

Este documento resume os **modelos de serviço na Azure (IaaS, PaaS, SaaS)** e o **Modelo de Responsabilidade Compartilhada**, com ênfase em **banco de dados** para apoiar o laboratório.

---

## 🎯 Objetivo de Aprendizagem
- Diferenciar **IaaS, PaaS e SaaS** no contexto da **Microsoft Azure**.  
- Compreender quem é responsável por quê no **Modelo de Responsabilidade Compartilhada**.  
- Relacionar os conceitos **ao cenário de banco de dados** (SQL no Azure).

---

## ☁️ Modelos de Serviço na Azure

### 🧱 IaaS — Infrastructure as a Service
**O que é:** Infraestrutura básica como VMs, redes e discos sob seu controle.  
**Exemplos Azure:** Azure Virtual Machines, Virtual Network, Managed Disks, Load Balancer.

**Banco de Dados em IaaS:**  
- **SQL Server em VM (Windows/Linux)**.  
- Você gerencia: SO, patches do SQL, **backups**, HA/DR, tuning, antivírus, NSG, atualizações.

**Quando usar:**  
- Requisitos de **customização total** do SO/SQL.  
- **Compatibilidade** com features específicas do SQL que não existem no PaaS.  
- Cenários de **migração “lift-and-shift”**.

---

### 🛠️ PaaS — Platform as a Service
**O que é:** Plataforma gerenciada; você foca no **código e nos dados**.  
**Exemplos Azure (App/Compute):** App Service, Azure Kubernetes Service (AKS – gerenciado), Azure Functions.  
**Exemplos Azure (Banco de Dados):** **Azure SQL Database**, **Azure SQL Managed Instance**, Azure Database for PostgreSQL/MySQL, Azure Cosmos DB.

**Banco de Dados em PaaS (foco):**  
- **Azure SQL Database** (single/elastic pool) e **Azure SQL Managed Instance** (compatibilidade avançada com SQL Server).  
- A Microsoft gerencia: **infra, SO, instância/engine, patching, alta disponibilidade e backups automáticos**.  
- Você gerencia: **esquema/dados**, usuários/roles, **políticas de backup/retention**, performance (índices/planos), rede (private endpoints), firewall e RBAC.

**Quando usar:**  
- Quer **reduzir operação** (menos patching/infra).  
- Precisa de **SLA, escalabilidade** e **recursos gerenciados** rapidamente.  
- Busca **compatibilidade com SQL Server** (Managed Instance) com menor esforço de gestão.

---

### 🧩 SaaS — Software as a Service
**O que é:** Aplicativo completo entregue como serviço; você usa e configura.  
**Exemplos Microsoft Cloud/Azure-adjacentes:** Microsoft 365, Dynamics 365, Power BI, Azure DevOps.

**Banco de Dados em SaaS (visão):**  
- O provedor **oculta a camada de banco**; você administra **usuários, permissões e dados** no contexto do app.  
- Pouca ou nenhuma gestão de engine/instância.

**Quando usar:**  
- **Time-to-value** imediato, sem gerenciar infraestrutura ou plataforma.  
- Requisitos atendidos por uma **aplicação pronta**.

---

## 🛡️ Modelo de Responsabilidade Compartilhada (Azure)

> A responsabilidade **migra do cliente para o provedor** conforme você sobe de IaaS → PaaS → SaaS.

| Camada / Tarefa                                        | IaaS                        | PaaS                               | SaaS                         |
|--------------------------------------------------------|-----------------------------|------------------------------------|------------------------------|
| Datacenter físico / energia / hardware                 | Provedor                    | Provedor                           | Provedor                     |
| Rede física / virtualização / armazenamento            | Provedor                    | Provedor                           | Provedor                     |
| **Sistema Operacional**                                | **Cliente**                 | Provedor                           | Provedor                     |
| **Engine/Runtime do Banco (SQL, patches)**             | **Cliente**                 | Provedor                           | Provedor                     |
| **Alta disponibilidade / DR (infra da plataforma)**    | **Cliente**                 | Provedor                           | Provedor                     |
| **Backups (execução)**                                 | **Cliente**                 | Provedor (config. pelo cliente)    | Provedor                     |
| **Rede lógica (NSG, Private Endpoint, Firewall)**      | Cliente                     | Cliente (regras/endereçamento)     | Provedor (limites) / Cliente |
| **Identidade e acesso (Microsoft Entra ID/RBAC)**      | Cliente                     | Cliente                            | Cliente                      |
| **Dados, schema, compliance, DLP, criptografia app**   | **Cliente**                 | **Cliente**                        | **Cliente**                  |
| **Configuração do aplicativo**                         | Cliente                     | Cliente                            | **Cliente**                  |

**Resumo prático para Banco de Dados:**  
- **SQL em VM (IaaS):** você faz **tudo** acima de hardware (SO, SQL, HA, backup, tuning).  
- **Azure SQL Managed Instance/Database (PaaS):** você foca em **dados, segurança lógica, rede e performance**; a plataforma cuida de engine, patching, HA e backups automáticos.  
- **SaaS:** você cuida de **dados e usuários** dentro do app; o resto é do provedor.

---

## 🧭 Escolha Rápida — Banco de Dados no Azure
- **Preciso de total controle e compatibilidade absoluta com features legadas:**  
  → **SQL Server em VM (IaaS)**.  
- **Quero compatibilidade alta com SQL Server, menos gestão e rede privada:**  
  → **Azure SQL Managed Instance (PaaS)**.  
- **Aplicação nova ou modernização com foco em PaaS e escala por database:**  
  → **Azure SQL Database (PaaS)**.  
- **Quero um app pronto (BI, ERP, colaboração):**  
  → **SaaS** (ex.: Power BI, Dynamics 365, Microsoft 365).

---

## 📚 Recurso Útil (da aula)
- Início Rápido: **Criar Instância Gerenciada de SQL no Azure**  
  https://learn.microsoft.com/pt-br/azure/azure-sql/managed-instance/instance-create-quickstart?view=azuresql&tabs=azure-portal

---

## 🧱 Como isso se conecta ao seu laboratório
- Ao **configurar uma instância de Banco de Dados no Azure**, você estará praticando **PaaS** (ex.: **Azure SQL Managed Instance**): menos gestão de engine, foco em **dados, segurança e rede**.  
- Use este conteúdo para **justificar suas decisões** no README do lab (por que PaaS vs IaaS, quais responsabilidades permanecem com você, como protegeu acesso com Entra ID/Firewall/Private Endpoint etc.).