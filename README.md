# Sistema de Gestão de Oficina de Carros

## 📌 Descrição do Projeto
Este projeto foi desenvolvido para representar, por meio de modelagem de banco de dados, o funcionamento de uma **oficina mecânica**.  
O sistema tem como objetivo organizar e controlar todas as informações relacionadas aos clientes, veículos, defeitos, mecânicos, pagamentos e entregas.  

No cenário proposto:
- O **cliente** leva o veículo até a oficina.
- O veículo é registrado no sistema, associando-o ao cliente.
- Um ou mais **defeitos** são identificados e registrados, juntamente com diagnóstico, peças necessárias, tipo de serviço e valor.
- Um **mecânico** é designado para realizar o conserto.
- Após o serviço, é registrado o **pagamento**, que pode ter diferentes formas e promoções.
- Por fim, ocorre a **entrega** do veículo ao cliente, com status e data documentados.

O modelo foi construído de forma a permitir:
- Controle total sobre cada etapa do processo.
- Relacionamento claro entre clientes, veículos e serviços prestados.
- Possibilidade de armazenar histórico de serviços e pagamentos.
- Flexibilidade para consultas e relatórios no banco de dados.

---

## 🖼 Diagrama do Sistema

![Diagrama da Oficina](diagrama_oficina.png)

---

## 📂 Entidades Principais

### **Cliente**
- Armazena informações pessoais do cliente como nome, endereço, cartão, CPF e telefone.
- Relaciona-se com **Veículos**, **Pagamentos** e **Entregas**.

### **Veículo**
- Contém dados do veículo como modelo, placa, ano e cor.
- Associado a um cliente e a possíveis **defeitos**.

### **Defeito_Veiculo**
- Registra os problemas identificados no veículo.
- Possui campos para descrição, peça envolvida, diagnóstico, tipo de serviço e valor.

### **Mecânico**
- Guarda informações sobre cada mecânico (nome, endereço, telefone e especialidade).
- Relaciona-se com os defeitos que conserta e com as entregas.

### **Pagamento**
- Registra o valor, forma de pagamento, promoções e os envolvidos na transação.
- Associado ao cliente, mecânico e defeito corrigido.

### **Entrega**
- Representa a finalização do serviço e entrega do veículo ao cliente.
- Armazena status e data da entrega.

---

## 🔗 Relacionamentos Importantes
- **Cliente ↔ Veículo**: Um cliente pode ter vários veículos.
- **Veículo ↔ Defeito_Veiculo**: Um veículo pode ter múltiplos defeitos.
- **Defeito_Veiculo ↔ Mecânico**: Um mecânico pode consertar vários defeitos e um defeito pode ser reparado por mais de um mecânico.
- **Pagamento**: Relaciona cliente, mecânico e defeito corrigido.
- **Entrega**: Conecta mecânico e cliente após a conclusão do serviço.

---

## ✅ Avaliação do Projeto

### Pontos Positivos
- Boa **organização das entidades** e relacionamentos.
- Uso adequado de **cardinalidades** (1:N, N:M).
- Presença de atributos relevantes para cada entidade.
- Inclusão de entidade intermediária **Pagamento** que relaciona múltiplos atores (cliente, mecânico, serviço).

### Possíveis Melhorias
- Revisar nomes das chaves estrangeiras para manter consistência.
- Verificar se alguns relacionamentos N:M não poderiam ser simplificados.
- Incluir **restrições de integridade** (por exemplo, NOT NULL, UNIQUE) diretamente no script do banco.
- Adicionar campos de auditoria (data de criação, última atualização).

---

## 🛠 Tecnologias Utilizadas
- MySQL Workbench (modelagem e diagramação)
- SQL (DDL e DML para criação e manipulação dos dados)

---

## 📄 Autor
Projeto desenvolvido como parte de estudo/avaliação sobre modelagem de banco de dados para sistemas de oficina mecânica.
