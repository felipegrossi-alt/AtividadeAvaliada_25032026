# Avaliação — Engenharia de Software
**Sistema Integrado de Gestão de Farmácia — MVP Definido pelo Estudante**

Aluno: Felipe Grossi Pereira 
RA: 25000473  
Data: 25/03/2026  

---

# 1. Definição do MVP
Descreva aqui **qual parte do sistema** foi incluída no seu MVP.  
Explique claramente: Criei uma versão do sistema que faz o básico para a farmácia funcionar. Ele identifica quem é o cliente, confere se o remédio tem na prateleira, registra a venda e imprime o cupom no final.

- O que está **dentro** do MVP:
Cadastrar e consultar os clientes, consultar os produtos, verificar o estoque, realizar vendas, atualizar automaticamente o estoque e emitir comprovante.

- O que está **fora** do MVP:
Comprar produtos dos fornecedores, controle dos fornecedores e pagar as contas da farmácia.

- Por que você fez essas escolhas: 
Foquei mais nos processos econômicos relacionado a vendas e a operação delas, por ser o que mais impacta no atendimento ao cliente.

Exemplo de início:  
> “Meu MVP cobre o processo de venda desde a identificação/cadastro do cliente até a emissão do comprovante, incluindo tratamento de estoque insuficiente.”

---

# 2. Regras de Negócio (mínimo: 5)
Liste e descreva **cada RN** de forma clara.

**RN01 —**  Não vender produtos fora de estoque.
**RN02 —**  Toda venda deve atualizar o estoque.
**RN03 —**  O sistema tem que calcular automaticamente o valor da venda.
**RN04 —**  Apenas farmacêuticos podem autorizar a venda de remédios controlados.
**RN05 —**  Contas a prazo só poderá ser feita por clientes cadastrados.

(Adicione mais se quiser.)

---

# 3. Requisitos Funcionais (mínimo: 8)
Liste os requisitos funcionais do seu MVP.

**RF01 —**  Cadastrar clientes.
**RF02 —**  Realizar vendas.
**RF03 —**  Ver o estoque antes de uma venda.
**RF04 —**  Registrar vendas a prazo.
**RF05 —**  Registrar vendas a vista.
**RF06 —**  Emitir comprovante da venda.
**RF07 —**  Atualizar o estoque pós compra.
**RF08 —**  Consultar produtos dentro do estoque.

(Adicione mais se quiser.)

---

# 🛡 4. Requisitos Não Funcionais (mínimo: 4)
Liste os RNFs do sistema conforme seu MVP.

**RNF01 —**  Integridade dos dados cadastrados pelos clientes.
**RNF02 —**  Integridade dos dados de vendas e do estoque.
**RNF03 —**  
**RNF04 —**  

(Adicione mais se quiser.)

---

# 5. Casos de Uso (mínimo: 10)
### Inserir **diagrama de casos de uso geral**, demonstrando claramente:
- os 10 casos
- relação entre eles e atores
- pelo menos 3 includes
- pelo menos 3 extends

---

# 6. Documentação dos Casos de Uso
Para **cada caso de uso**, utilize o template abaixo:
---

## **UCXX — Nome do Caso de Uso**
**Ator(es):**  
**Descrição:**  
**Pré-condições:**  
**Pós-condições:**  

### Fluxo Principal
1.  
2.  
3.  
4.  

### Fluxos Alternativos / Exceções
- FA01 —  
- FA02 —  

### Relacionamentos
- **Include:** (listar quando aplicável)  
- **Extend:** (listar quando aplicável)  

### Inserir o diagrama de atividades do Caso de Uso, demonstrando tudo o fluxo princial e alternativos/exceções.

---

> Repita essa estrutura para **todos os seus casos de uso** (mínimo 10).


