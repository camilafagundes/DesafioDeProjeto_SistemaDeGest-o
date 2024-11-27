# Desafio de Projeto: Sistema de Gestão de Contas, Pagamentos e Entregas

## Descrição do Projeto Conceitual

Este projeto tem como objetivo desenvolver um modelo conceitual para um sistema de gestão de contas de clientes, pagamentos e entregas. O sistema será projetado para acomodar tanto clientes pessoa jurídica (PJ) quanto clientes pessoa física (PF), mantendo informações separadas para cada tipo de cliente. Além disso, a solução permitirá que um cliente tenha múltiplas formas de pagamento cadastradas e possibilitará o gerenciamento de entregas, com acompanhamento através de status e códigos de rastreio.

O sistema deve ser flexível, escalável e capaz de atender a diferentes necessidades de gestão de contas, pagamentos e entregas, com uma estrutura de dados bem definida e clara.

## Objetivos de Refinamento do Modelo

1. **Cliente PJ e PF**
- O sistema deverá permitir que um cliente seja classificado como Pessoa Jurídica (PJ) ou Pessoa Física (PF).
- Cada conta de cliente pode ser associada a apenas um tipo de cliente (PJ ou PF), e não será possível associar ambos os tipos a uma única conta.
- Os dados de cliente terão atributos específicos dependendo do tipo (exemplo: CNPJ para PJ, CPF para PF).
2. **Pagamento**
- O cliente poderá ter mais de uma forma de pagamento associada à sua conta.
- Cada forma de pagamento terá seus dados específicos (exemplo: número do cartão de crédito, conta bancária, etc.).
- A possibilidade de múltiplos métodos de pagamento deve ser registrada de forma a permitir que o cliente altere suas formas de pagamento conforme necessário.
3. **Entrega**
- O sistema gerenciará as entregas associadas a cada cliente e pedido.
- Cada entrega terá um status associado (exemplo: "Em andamento", "Entregue", "Cancelado", etc.).
- Cada entrega também possuirá um código de rastreio para que o cliente possa acompanhar o andamento da entrega em tempo real.

## Modelo de Dados

### Entidades Principais

**Cliente**

- ID: Identificador único do cliente.
- Tipo de Cliente: PJ ou PF (não podem ser ambos).
- Dados Pessoais: Dependem do tipo (CNPJ ou CPF).
- Endereço: Endereço de cobrança e entrega.
- Formas de Pagamento: Relacionamento de um cliente com suas formas de pagamento.

**Forma de Pagamento**

- ID: Identificador único da forma de pagamento.
- Tipo: Cartão de Crédito, Débito, Boleto Bancário, etc.
- Detalhes: Informações específicas, como número do cartão ou dados bancários.
- Cliente: Relacionamento com o cliente associado.

**Entrega**

- ID: Identificador único da entrega.
- Status: Exemplo: "Em andamento", "Entregue", "Cancelado".
- Código de Rastreamento: Código único para rastrear a entrega.
- Pedido: Relacionamento com o pedido ao qual a entrega está associada.

**Relacionamentos**

**Cliente -> Forma de Pagamento:** Um cliente pode ter múltiplas formas de pagamento.
**Pedido -> Entrega:** Um pedido pode ter uma ou mais entregas associadas.
**Entrega -> Status:** Cada entrega tem um status associado.

**Tecnologias Utilizadas**

- Banco de Dados: SQL ou NoSQL (dependendo do tipo de dados e escalabilidade desejada).
- Frameworks: A ser definido dependendo das necessidades do projeto (exemplo: Django, Flask, Node.js, etc.).
- Ferramentas de Rastreamento: APIs externas para rastreio de entregas, como Correios ou outras transportadoras.
