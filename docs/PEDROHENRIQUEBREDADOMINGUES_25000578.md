# Avaliação — Engenharia de Software
Sistema Integrado de Gestão de Farmácia — MVP Definido pelo Estudante

Aluno: Pedro Henrique Breda Domingues  
RA: 25000578  
Data: 25/03/2026  

---

# 1. Definição do MVP

Meu MVP cobre o processo de venda dentro da farmácia, desde quando o cliente chega até a finalização da compra com o comprovante.

O que está dentro do MVP  
- Consulta de produtos  
- Verificação de estoque  
- Cadastro de cliente  
- Registro da venda  
- Emissão de comprovante  
- Venda à vista e a prazo  

O que está fora do MVP  
- Cadastro de fornecedores  
- Compras de produtos  
- Relatórios mais avançados  
- Parte administrativa completa  

Por que essas escolhas  

Escolhi focar na venda porque é a principal atividade da farmácia. Também envolve várias partes importantes como cliente, estoque e pagamento.

---

# 2. Regras de Negócio

RN01 — Não vender produto sem estoque  
A venda só pode acontecer se houver quantidade disponível no estoque  

RN02 — Toda venda precisa ter um cliente  
Não é permitido finalizar venda sem identificar o cliente  

RN03 — Venda a prazo gera conta a receber  
Sempre que o pagamento não for à vista, o valor deve ser registrado para recebimento futuro  

RN04 — Produto precisa estar cadastrado  
Só é possível vender produtos que já existem no cadastro  

RN05 — Atualização automática de estoque  
Depois de cada venda, a quantidade disponível deve ser reduzida automaticamente  

RN06 — Não vender produto inexistente  
Caso o produto não seja encontrado, a venda não pode continuar  

---

# 3. Requisitos Funcionais

RF01 — Cadastro de clientes  
Permitir registrar novos clientes no sistema  

RF02 — Consulta de produtos  
Permitir buscar produtos por nome ou código  

RF03 — Registro de vendas  
Permitir realizar vendas de produtos  

RF04 — Verificação de estoque  
Antes da venda, conferir se há quantidade disponível  

RF05 — Atualização de estoque  
Após a venda, diminuir a quantidade automaticamente  

RF06 — Emissão de comprovante  
Gerar um comprovante com os dados da venda  

RF07 — Venda à vista e a prazo  
Permitir escolher forma de pagamento  

RF08 — Registro de contas a receber  
Guardar informações de pagamentos futuros  

RF09 — Cadastro de produtos  
Permitir adicionar novos produtos  

---

# .4. Requisitos Não Funcionais

RNF01 — Resposta rápida  
As ações devem acontecer sem demora perceptível  

RNF02 — Controle de acesso  
O acesso deve ser feito com login  

RNF03 — Disponibilidade  
O sistema deve funcionar durante o horário de uso da farmácia  

RNF04 — Facilidade de uso  
A interface deve ser simples e fácil de entender  

RNF05 — Integridade dos dados  
As informações não devem ser perdidas ou alteradas incorretamente  

---

# 5. Casos de Uso

Inserir aqui o diagrama de casos de uso geral contendo:

- UC01 — Realizar Venda  
- UC02 — Consultar Produto  
- UC03 — Verificar Estoque  
- UC04 — Cadastrar Cliente  
- UC05 — Emitir Comprovante  
- UC06 — Registrar Conta a Receber  
- UC07 — Cadastrar Produto  
- UC08 — Atualizar Estoque  
- UC09 — Selecionar Forma de Pagamento  
- UC10 — Cancelar Venda  

Atores:
- Atendente  
- Gerente  
- Sistema  

Relacionamentos esperados:
- Includes: Consultar Produto, Verificar Estoque, Atualizar Estoque  
- Extends: Cadastrar Cliente, Registrar Conta a Receber, Cancelar Venda  

<img width="1135" height="698" alt="image" src="https://github.com/user-attachments/assets/561df47e-9dec-4f1f-91db-1aa12c16a1cc" />


---

# 6. Documentação dos Casos de Uso

## UC01 — Realizar Venda
Ator(es): Atendente  
Descrição: Registrar a venda de produtos para um cliente  

Pré-condições  
Cliente identificado  
Produto cadastrado  

Pós-condições  
Venda registrada  
Estoque atualizado  

Fluxo Principal  
1. Atendente inicia a venda  
2. Cliente é informado  
3. Produto é selecionado  
4. Quantidade é definida  
5. Estoque é verificado  
6. Valor é calculado  
7. Venda é confirmada  
8. Registro da venda é feito  
9. Estoque é atualizado  

Fluxos Alternativos / Exceções  

FA01 — Cliente não cadastrado  
Permitir cadastro rápido antes de continuar  

FA02 — Estoque insuficiente  
Exibir aviso e impedir continuação  

Relacionamentos  
Include: Consultar Produto, Verificar Estoque  
Extend: Cadastrar Cliente  

<img width="324" height="861" alt="image" src="https://github.com/user-attachments/assets/eec53e11-5f1d-4858-bbd2-f80861dc7308" />
 

---

## UC02 — Consultar Produto
Ator(es): Atendente  
Descrição: Buscar produtos cadastrados  

Pré-condições  
Sistema disponível  

Pós-condições  
Lista de produtos exibida  

Fluxo Principal  
1. Atendente acessa a busca  
2. Informa nome ou código  
3. Sistema retorna resultados  

Fluxos Alternativos  

FA01 — Produto não encontrado  
Exibir mensagem  

Relacionamentos  
Include:  
Extend:  

<img width="340" height="453" alt="image" src="https://github.com/user-attachments/assets/c0ecd7a1-b715-4426-b5f7-584e22e154b5" />


---

## UC03 — Verificar Estoque
Ator(es): Sistema  
Descrição: Conferir quantidade disponível  

Pré-condições  
Produto selecionado  

Pós-condições  
Quantidade exibida  

Fluxo Principal  
1. Sistema recebe produto  
2. Consulta estoque  
3. Retorna quantidade  

Fluxos Alternativos  

FA01 — Produto não encontrado  

Relacionamentos  
Include:  
Extend:  

<img width="395" height="385" alt="image" src="https://github.com/user-attachments/assets/c9f6be4e-c942-49e3-b91d-95285c350e8e" />


---

## UC04 — Cadastrar Cliente
Ator(es): Atendente  
Descrição: Registrar um novo cliente  

Pré-condições  
Dados disponíveis  

Pós-condições  
Cliente cadastrado  

Fluxo Principal  
1. Inserir dados  
2. Validar  
3. Salvar  

Fluxos Alternativos  

FA01 — Dados inválidos  

Relacionamentos  
Include:  
Extend:  

<img width="259" height="385" alt="image" src="https://github.com/user-attachments/assets/a758721f-d7b1-46f3-8987-54911d7cf319" />


---

## UC05 — Emitir Comprovante
Ator(es): Sistema  
Descrição: Gerar comprovante da venda  

Pré-condições  
Venda finalizada  

Pós-condições  
Comprovante gerado  

Fluxo Principal  
1. Coletar dados  
2. Gerar comprovante  
3. Exibir  

Fluxos Alternativos  

FA01 — Falha na geração  

Relacionamentos  
Include:  
Extend:  

<img width="338" height="385" alt="image" src="https://github.com/user-attachments/assets/311686f6-5289-4003-bd0d-071226ba3285" />


---

## UC06 — Registrar Conta a Receber
Ator(es): Sistema  
Descrição: Registrar valor de venda a prazo  

Pré-condições  
Venda a prazo  

Pós-condições  
Conta registrada  

Fluxo Principal  
1. Identificar valor  
2. Registrar  
3. Salvar  

Fluxos Alternativos  

FA01 — Erro no registro  

Relacionamentos  
Include:  Selecionar Forma de Pagamento
Extend:  

<img width="168" height="489" alt="image" src="https://github.com/user-attachments/assets/51398116-2117-4213-8d9e-9d3e43302ae1" />


---

## UC07 — Cadastrar Produto
Ator(es): Gerente  
Descrição: Adicionar novos produtos  

Pré-condições  
Dados disponíveis  

Pós-condições  
Produto cadastrado  

Fluxo Principal  
1. Inserir dados  
2. Salvar  

Fluxos Alternativos  

FA01 — Dados inválidos  

Relacionamentos  
Include:  
Extend:  

<img width="304" height="385" alt="image" src="https://github.com/user-attachments/assets/bcb4722d-bdb5-4cce-b8dc-d910919f6f47" />
 

---

## UC08 — Atualizar Estoque
Ator(es): Sistema  
Descrição: Atualizar quantidade após venda  

Pré-condições  
Venda realizada  

Pós-condições  
Estoque atualizado  

Fluxo Principal  
1. Subtrair quantidade  
2. Atualizar registro  

Fluxos Alternativos  

FA01 — Erro na atualização  

Relacionamentos  
Include: Realizar Venda 
Extend:  

<img width="292" height="385" alt="image" src="https://github.com/user-attachments/assets/7a0e5e17-288b-400d-ab89-fb2aaf13b99e" />
  

---

## UC09 — Selecionar Forma de Pagamento
Atores: Atendente  
Descrição: Escolher pagamento à vista ou a prazo  

Pré-condições  
Venda em andamento  

Pós-condições  
Forma definida  

Fluxo Principal  
1. Exibir opções  
2. Selecionar  
3. Confirmar  

Fluxos Alternativos  

FA01 — Opção inválida  

Relacionamentos  
Include:  
Extend:  Registrar Conta a Receber

<img width="269" height="385" alt="image" src="https://github.com/user-attachments/assets/3248d50d-5880-45fd-8f13-59f6243d3641" />


---

## UC10 — Cancelar Venda
Atores: Atendente  
Descrição: Cancelar uma venda iniciada  

Pré-condições  
Venda em andamento  

Pós-condições  
Venda cancelada  

Fluxo Principal  
1. Solicitar cancelamento  
2. Confirmar  
3. Encerrar  

Fluxos Alternativos  

FA01 — Cancelamento negado  

Relacionamentos  
Include:  
Extend:  Realizar Venda

<img width="298" height="317" alt="image" src="https://github.com/user-attachments/assets/a3361f4b-b325-475c-abd0-dc5def9f94cc" />


---
