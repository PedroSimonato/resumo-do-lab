# Resumo do Lab — Computação em Nuvem (DIO)

> Repositório com o resumo das lições aprendidas sobre **computação em nuvem**, modelos de implantação e serviço, **responsabilidade compartilhada** e **CapEx vs. OpEx**.

## 📌 Sumário
- [O que é Computação em Nuvem](#o-que-é-computação-em-nuvem)
- [Modelos de implantação: Privada, Pública e Híbrida](#modelos-de-implantação-privada-pública-e-híbrida)
- [Comparativo entre os modelos de implantação](#comparativo-entre-os-modelos-de-implantação)
- [Modelos de serviço: IaaS, PaaS e SaaS](#modelos-de-serviço-iaas-paas-e-saas)
- [Responsabilidade Compartilhada](#responsabilidade-compartilhada)
- [CapEx vs. OpEx](#capex-vs-opex)
- [Principais aprendizados do lab](#principais-aprendizados-do-lab)

---

## O que é Computação em Nuvem
Computação em nuvem é o fornecimento de recursos de TI (**servidores, armazenamento, redes, bancos de dados, analytics e software**) como serviços sob demanda, via internet, com pagamento conforme o uso. O objetivo é **agilidade, elasticidade, alta disponibilidade e otimização de custos** sem a necessidade de gerenciar toda a infraestrutura física.

---

## Modelos de implantação: Privada, Pública e Híbrida

### 🔐 Nuvem Privada
- **Definição:** Infraestrutura dedicada a uma única organização (on-premises ou hospedada).
- **Vantagens:** Alto controle, personalização, compliance mais rígido.
- **Desafios:** Custos iniciais maiores e menor elasticidade que nuvem pública.
- **Cenários típicos:** Setores regulados, dados sensíveis, workloads legados.

### ☁️ Nuvem Pública
- **Definição:** Recursos oferecidos por um provedor a múltiplos clientes em ambiente multi-tenant.
- **Vantagens:** Elasticidade, escala global, time-to-market rápido, modelo pay-as-you-go.
- **Desafios:** Menor controle fino do hardware, dependência do provedor.
- **Cenários típicos:** Aplicações web/microserviços, picos sazonais, inovação rápida.

### 🌉 Nuvem Híbrida
- **Definição:** Combina nuvem privada e pública com **portabilidade** e **integração** entre cargas.
- **Vantagens:** Flexibilidade para manter dados sensíveis on-premises e escalar na pública.
- **Desafios:** Complexidade de redes, identidade e governança.
- **Cenários típicos:** Migrações graduais, requisitos legais de dados, burst de capacidade.

---

## Comparativo entre os modelos de implantação

| Critério            | Privada                          | Pública                              | Híbrida                                       |
|---------------------|----------------------------------|--------------------------------------|-----------------------------------------------|
| Propriedade         | Dedicada à organização           | Do provedor (multi-tenant)           | Mista (org + provedor)                        |
| Controle            | Máximo                           | Médio                                | Alto (com complexidade)                       |
| Elasticidade        | Limitada                          | Muito alta                           | Alta (com orquestração)                       |
| Custo inicial       | Alto (CapEx)                      | Baixo (OpEx)                         | Variável (CapEx + OpEx)                       |
| Compliance          | Facilitada                        | Depende de serviços/regiões          | Boa, com desenho adequado                     |
| Casos comuns        | Dados sensíveis, legado           | Apps web, experimentação, escala     | Migração, requisitos legais, burst sazonal    |

---

## Modelos de serviço: IaaS, PaaS e SaaS

### 🧱 IaaS (Infrastructure as a Service)
- **O que entrega:** Infraestrutura básica (VMs, storage, redes).
- **Você gerencia:** SO, runtime, aplicação e dados.
- **Quando usar:** Máxima flexibilidade, lift-and-shift, customizações profundas.

### 🛠️ PaaS (Platform as a Service)
- **O que entrega:** Plataforma gerenciada (runtime, autoscaling, DB como serviço).
- **Você gerencia:** Código e dados da aplicação.
- **Quando usar:** Foco em desenvolvimento, menos operação.

### 🧩 SaaS (Software as a Service)
- **O que entrega:** Aplicativo completo pronto para uso.
- **Você gerencia:** Configurações e dados do seu uso.
- **Quando usar:** Produtividade rápida, menor esforço de TI.

---

## Responsabilidade Compartilhada

Quem cuida de quê varia por **modelo de serviço**. Em geral, **quanto mais gerenciado**, mais responsabilidade migra para o provedor.

| Camada / Modelo | IaaS (Prov / Cliente) | PaaS (Prov / Cliente) | SaaS (Prov / Cliente) |
|-----------------|------------------------|------------------------|------------------------|
| Datacenter físico, energia, hardware | **Prov** | **Prov** | **Prov** |
| Rede, storage, virtualização         | **Prov** | **Prov** | **Prov** |
| Sistema Operacional                  | Cliente  | **Prov** | **Prov** |
| Runtime/Framework                    | Cliente  | **Prov** | **Prov** |
| Aplicação                            | Cliente  | Cliente  | **Prov** |
| Configuração de acesso               | Cliente  | Cliente  | Cliente  |
| Dados e identidade do usuário        | Cliente  | Cliente  | Cliente  |
| Segurança de conteúdo                | Cliente  | Cliente  | Cliente  |

> **Resumo:** o provedor protege a **infraestrutura**; o cliente protege **acessos, dados e configurações** daquilo que usa.

---

## CapEx vs. OpEx

- **CapEx (Capital Expenditure):** investimento de capital (compra de servidores, licenças perpétuas, datacenter). Impacto contábil ao **imobilizar** ativos.
- **OpEx (Operational Expenditure):** despesa operacional recorrente (assinaturas, consumo na nuvem, suporte). Impacto no **resultado** do período.

| Aspecto           | CapEx                               | OpEx                                 |
|-------------------|-------------------------------------|---------------------------------------|
| Entrada de caixa  | Alta, antecipada                     | Baixa, diluída                        |
| Flexibilidade     | Menor (capacidade fixa)              | Maior (pague pelo uso)                |
| Escalabilidade    | Lenta (aquisição/instalação)         | Rápida (provisionamento em minutos)   |
| Aderência à nuvem | Menor                                | Maior (modelo típico da nuvem)        |

> **Aprendizado-chave:** a nuvem favorece **OpEx** e **elasticidade**, reduzindo risco de superdimensionamento e encurtando o time-to-market.

---

## Principais aprendizados do lab
- Diferenciei **modelos de implantação** (Privada, Pública, Híbrida) e quando cada um faz sentido.
- Entendi **IaaS, PaaS e SaaS** e como isso impacta **o que eu gerencio** vs. **o que o provedor gerencia**.
- Compreendi o **modelo de responsabilidade compartilhada** e a importância de configurar **identidade, acesso e proteção de dados** corretamente.
- Analisei **CapEx vs. OpEx** e como a nuvem permite **custos proporcionais ao uso** e **escala sob demanda**.
- Reforcei boas práticas: **governança**, **segurança por padrão**, **observabilidade** e **otimização de custos** desde o início.

---

> 💡 **Dica:** personalize este README com exemplos da sua experiência (ex.: serviços que você usaria para IaaS/PaaS/SaaS, decisões de implantação no seu contexto, e aprendizados específicos do seu lab).
