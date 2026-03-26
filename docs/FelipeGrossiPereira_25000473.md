# Avaliação — Engenharia de Software
**Sistema Integrado de Gestão de Farmácia — MVP Definido pelo Estudante**

Aluno: Felipe Grossi Pereira 
RA: 25000473  
Data: 25/03/2026  

---

# 1. Definição do MVP  
Explique claramente: Criei uma versão do sistema que faz o básico para a farmácia funcionar. Ele identifica quem é o cliente, confere se o remédio tem na prateleira, registra a venda e imprime o cupom no final.

- **dentro** do MVP:
Cadastrar e consultar os clientes, consultar os produtos, verificar o estoque, realizar vendas, atualizar automaticamente o estoque e emitir comprovante.

- **fora** do MVP:
Comprar produtos dos fornecedores, controle dos fornecedores e pagar as contas da farmácia.

- Por que você fez essas escolhas: 
Foquei mais nos processos econômicos relacionado a vendas e a operação delas, por ser o que mais impacta no atendimento ao cliente.

---

# 2. Regras de Negócio (mínimo: 5)

**RN01 —**  Não vender produtos fora de estoque.
**RN02 —**  Toda venda deve atualizar o estoque.
**RN03 —**  O sistema tem que calcular automaticamente o valor da venda.
**RN04 —**  Apenas farmacêuticos podem autorizar a venda de remédios controlados.
**RN05 —**  Contas a prazo só poderá ser feita por clientes cadastrados.

---

# 3. Requisitos Funcionais (mínimo: 8)

**RF01 —**  Cadastrar clientes.
**RF02 —**  Realizar vendas.
**RF03 —**  Ver o estoque antes de uma venda.
**RF04 —**  Registrar vendas a prazo.
**RF05 —**  Registrar vendas a vista.
**RF06 —**  Emitir comprovante da venda.
**RF07 —**  Atualizar o estoque pós compra.
**RF08 —**  Consultar produtos dentro do estoque.

---

# 4. Requisitos Não Funcionais (mínimo: 4)

**RNF01 —**  Integridade dos dados cadastrados pelos clientes.
**RNF02 —**  Integridade dos dados de vendas e do estoque.
**RNF03 —**  O sistema tem que estar em funcionamento e horário comercial.
**RNF04 —**  O sistema tem que processar tudo em pelo menos 5 segundos.

---

# 5. Documentação dos Casos de Uso

## **UC01 — Identificar Cliente**
**Ator(es): Atendente**  
**Descrição: Buscar no sistema o cliente**  
**Pré-condições: Sistema estar funcionando**  
**Pós-condições: Cliente identificado**  

### Fluxo Principal
1.  Informa nome do cliente ou o CPF.
2.  O sistema busca o cliente no banco de dados.
3.  Exibe todos os dados do cliente. 

### Fluxos Alternativos / Exceções
- FA01 —  Se não estiver cadastrado ainda, aparecer uma informação de cadastro.
<img width="395" height="312" alt="image" src="https://github.com/user-attachments/assets/a7f8a0a5-e54f-4769-b10b-a341fe25247c" />


## **UC02 — Cadastrar Cliente**
**Ator(es): Atendendte**  
**Descrição: Cadastrar um cliente no sistema**  
**Pré-condições: Cliente não estar no sistema**  
**Pós-condições: Cliente cadastrado**  

### Fluxo Principal
1.  Informa os dados do cliente.
2.  Sistema receber esses dados.
3.  Validar os dados. 
4.  Cliente cadastrado.
   
### Fluxos Alternativos / Exceções
- FA01 —  Se algum dado estiver errado, ter a opção de tentar novamente.

### Relacionamentos
- Extend: Realizar Venda
<img width="325" height="440" alt="image" src="https://github.com/user-attachments/assets/3910e213-fa66-4e63-a550-2f7b892b2a68" />
  

## **UC03 — Consultar produto**
**Ator(es): Atendendte**  
**Descrição: Buscar produto na base de dados**  
**Pré-condições: Ter o produto no estoque**  
**Pós-condições: Exibir o produto**  

### Fluxo Principal
1.  Informar nome do produto
2.  Realizar a busca do produto
3.  Atendente seleciona o produto
   
### Fluxos Alternativos / Exceções
- FA01 —  Se não tiver o produto, informar que não tem no estoque.
<img width="330" height="367" alt="image" src="https://github.com/user-attachments/assets/23768282-4f85-489c-8c4b-50607abab2d9" />


## **UC04 — Verificar o estoque**
**Ator(es): Sistema**  
**Descrição: Verifica quanto que tem do produto**  
**Pré-condições: Ter o produto no estoque**  
**Pós-condições: Exibir a quantidade**  

### Fluxo Principal
1.  Procura a quantidade que tem no estoque.
2.  Olha se tem o suficiente de acordo com o que foi solicitado.
3.  Informa a disponibilidade do produto.
   
### Fluxos Alternativos / Exceções
- FA01 —  Se não tiver disponibilidade, mostrará que não tem o suficiente.
<img width="376" height="312" alt="image" src="https://github.com/user-attachments/assets/b8454530-2bf3-4aba-9a8f-671afd9e2e1b" />



## **UC05 — Fazer a venda**
**Ator(es): Atendente**  
**Descrição: Realizar uma venda dentro do sistema**  
**Pré-condições: Ter o produto no estoque**  
**Pós-condições: Venda feita**  

### Fluxo Principal

1.  Identificar o cliente.
2.  Consultar o produto no banco de dados.
3.  Informar a quantidade solicitada.
4.  Verificar o estoque.
5.  Calcula o valor da venda.
6.  Confirmar a venda.
7.  Imprimir o recibo.
   
### Fluxos Alternativos / Exceções
- FA01 —  Se não identificar o cliente, aparecer para cadastrar. 
- FA02 —  Se não estiver o suficiente no estoque, aparecer a quantidade que tem.
  
### Relacionamentos
- Include: Identificar Cliente, Consultar Produto, Verificar Estoque
- Extend: Cadastrar Cliente, Registrar Venda a Prazo, Autorizar Medicamento
<img width="358" height="532" alt="image" src="https://github.com/user-attachments/assets/dc931c42-d6df-4261-915d-24081e7b4b44" />


## **UC06 — Venda a vista**
**Ator(es): Atendente**  
**Descrição: Realizar uma venda dentro do sistema com o pagamento na hora**  
**Pré-condições: Ter o produto no estoque**  
**Pós-condições: Venda feita**  

### Fluxo Principal

1.  Selecionar que o pagamento vai ser a vista.
2.  Receber o pagamento.
3.  Venda feita.

### Fluxos Alternativos / Exceções
- FA01 —  Se der falha no pagamento, aparecer para cancelar a compra.

### Relacionamentos
- Extend: Realizar Venda.
<img width="282" height="312" alt="image" src="https://github.com/user-attachments/assets/fd86f424-d58f-4f76-b446-27f2f377c11e" />
  

## **UC07 — Venda a fiado**
**Ator(es): Atendente**  
**Descrição: Permitir que o cliente cadastrado possa pagar depois**  
**Pré-condições: Cliente cadastrado**  
**Pós-condições: Notinha para receber**  

### Fluxo Principal

1.  Selecionar que o pagamento vai ser a fiado.
2.  Sistema busca no banco de dados para ver se o cliente está cadastrado.
3.  Gerar a notinha para receber.
   
### Fluxos Alternativos / Exceções
- FA01 —  Se não identificar o cliente, aparecer para cadastrar. 
- FA02 —  Cancelar a compra se o cliente não for cadastrado.
  
### Relacionamentos
- Include: Gerar a notinha.
- Extend: Realizar Venda.
<img width="267" height="367" alt="image" src="https://github.com/user-attachments/assets/66a6580f-d1d3-4394-8dd2-a20643355cf5" />


## **UC08 — Gerar notinha**
**Ator(es): Sistema**  
**Descrição: Gerar uma notinha para que o cliente possa pagar depois.**  
**Pré-condições: Realizar venda a fiado**  
**Pós-condições: Notinha gerada**  

### Fluxo Principal

1.  Receber os dados da venda.
2.  Definir o vencimento da notinha.
3.  Gerar a notinha.
<img width="180" height="248" alt="image" src="https://github.com/user-attachments/assets/bad1bb0b-f273-4160-b272-39ebd186be55" />


## **UC09 — Gerar o comprovante**
**Ator(es): Sistema**  
**Descrição: Gerar o comprovante da venda**  
**Pré-condições: Vendar ser feita**  
**Pós-condições: Emitir o comprovante**  

### Fluxo Principal

1.  O sistema pega os dados da venda
2.  Gera o comprovante.
3.  Opção de imprimir.

### Relacionamentos
- Extend: Realizar Venda.
<img width="173" height="248" alt="image" src="https://github.com/user-attachments/assets/b5d463ed-4391-44a5-9cff-93e51e6dd76c" />


## **UC10 — Medicamento controlado**
**Ator(es): Farmacêutico**  
**Descrição: O farmacêutico vai autorizar a venda do remédio controlado**  
**Pré-condições: Provar que é farmacêutico**  
**Pós-condições: Autorizar a venda**  

### Fluxo Principal

1.  O sistema identifica se o produto é controlado.
2.  Validar a receita do remédio.
3.  Autorizar a venda do remédio
   
### Fluxos Alternativos / Exceções
- FA01 —  Se não identificar que é um farmacêutico de verdade, cancelar a venda.
  
### Relacionamentos
- Extend: Realizar Venda.
<img width="251" height="312" alt="image" src="https://github.com/user-attachments/assets/52030c77-b456-4677-ba26-03ceb1934e5c" />
