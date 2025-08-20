# Resumo do Lab — Máquinas Virtuais no Azure (DIO)

Este repositório contém o resumo das atividades realizadas e os aprendizados adquiridos durante o **desafio de máquinas virtuais no Microsoft Azure**, proposto pela Digital Innovation One (DIO).  

---

## 📌 Objetivos do Desafio
- Consolidar o conhecimento sobre **máquinas virtuais (VMs)** no Azure.  
- Aplicar conceitos práticos aprendidos em aula.  
- Documentar o processo técnico de forma clara e estruturada.  
- Utilizar o **GitHub** como ferramenta de documentação e compartilhamento.  

---

## 🖥️ Passos Realizados

### 1. Criação da Máquina Virtual
- Acesse o [Portal do Azure](https://portal.azure.com).  
- Escolha **Máquinas Virtuais** > **Criar** > **Máquina Virtual do Windows**.  
- Configure os seguintes parâmetros principais:
  - **Grupo de Recursos (Resource Group):** criado para organizar os recursos.  
  - **Nome da VM:** `lab-vm-dio`.  
  - **Região:** próxima para melhor desempenho.  
  - **Imagem:** Windows Server 2019 Datacenter (exemplo).  
  - **Tamanho:** configurado de acordo com as necessidades (exemplo: B1s para testes).  
  - **Autenticação:** usuário e senha definidos.  

### 2. Configuração de Rede
- Criado **IP público** para acesso remoto.  
- Porta **RDP (3389)** liberada para conexão.  
- Grupo de Segurança de Rede (NSG) configurado com regras mínimas necessárias.  

### 3. Conexão com a VM
- Acesso realizado via **Remote Desktop (RDP)** usando o IP público e as credenciais criadas.  
- Validação do funcionamento do sistema operacional instalado.  

### 4. Gerenciamento da VM
- Testes de iniciar/parar/reiniciar a máquina pelo Portal do Azure.  
- Observação de como o consumo impacta nos **custos sob demanda**.  
- Importância de **parar/desalocar** a VM quando não estiver em uso.  

---

## 🌐 Benefícios da Computação em Nuvem

Durante o lab também foi possível reforçar os principais **benefícios da nuvem**, que justificam sua ampla adoção no mercado:

### 📈 Escalabilidade
- Capacidade de **aumentar ou reduzir recursos** de acordo com a demanda da aplicação ou do negócio.  
- Permite atender grandes volumes de usuários sem perda de desempenho.

### 🔄 Elasticidade
- Recursos podem ser **provisionados e liberados automaticamente** sob demanda.  
- Evita gastos desnecessários e garante eficiência.

### ⚡ Alta Disponibilidade
- Serviços desenhados para minimizar indisponibilidades, garantindo **tempo de atividade contínuo**.  
- Uso de **zonas de disponibilidade** e redundância geográfica.

### 🔒 Confiabilidade
- Dados armazenados com **replicação automática** e suporte a **recuperação de desastres**.  
- Maior confiança na execução das cargas de trabalho críticas.

### 📊 Previsibilidade
- Custos controlados por meio do modelo **pay-as-you-go** e ferramentas de monitoramento.  
- Empresas podem prever tanto **desempenho** quanto **orçamento**.

### 🛡️ Segurança
- Provedores oferecem recursos avançados de **criptografia, firewalls, monitoramento e identidade**.  
- Certificações internacionais ajudam a atender requisitos de conformidade.

### 🏛️ Governança
- Ferramentas de políticas, auditoria e monitoramento permitem **controle centralizado**.  
- Suporte à adequação a leis e regulamentos (LGPD, GDPR, HIPAA, etc).

### ⚙️ Gerenciabilidade
- Interfaces amigáveis (Portal, CLI, APIs) e **monitoramento integrado**.  
- Automação via scripts e integrações com DevOps facilitam a operação diária.

---

> ✅ Esses benefícios tornam a nuvem uma plataforma estratégica para inovação, redução de custos e maior segurança operacional.