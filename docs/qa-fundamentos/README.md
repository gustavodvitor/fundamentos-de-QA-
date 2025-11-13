# 🧪 15 Casos de Teste + 5 Bug Reports Profissionais

---

## 1) 15 Casos de Teste (Login, Cadastro, Checkout)

---

# 🔐 Login (5 Casos)

---

### **CT-01 – Login com credenciais válidas**
**Módulo:** Login  
**Objetivo:** Validar que o usuário consegue acessar o sistema com e-mail e senha corretos.  

**Pré-condição:**  
- Usuário já cadastrado: `aluno@unifei.edu.br`, senha: `Senha123`.

**Passos:**
1. Acessar a página de login.
2. Informar e-mail `aluno@unifei.edu.br`.
3. Informar senha `Senha123`.
4. Clicar em **Entrar**.

**Resultado esperado:**  
- Login efetuado com sucesso.  
- Redirecionar para o Dashboard.  
- Exibir “Bem-vindo, [Nome do usuário]”.

---

### **CT-02 – Login com senha inválida**
**Objetivo:** Verificar mensagem de erro ao informar senha incorreta.

**Pré-condição:**  
- Usuário cadastrado.

**Passos:**
1. Acessar login.
2. Informar e-mail válido.
3. Informar senha incorreta.
4. Clicar em **Entrar**.

**Resultado esperado:**  
- Mostrar “E-mail ou senha inválidos”.

---

### **CT-03 – Login com e-mail em branco**
**Objetivo:** Validar obrigatoriedade do campo e-mail.

**Passos:**
1. Acessar login.
2. Deixar e-mail em branco.
3. Informar uma senha qualquer.
4. Clicar em **Entrar**.

**Resultado esperado:**  
- Mostrar “Campo obrigatório”.

---

### **CT-04 – Login com formato de e-mail inválido**
**Objetivo:** Validar formato do e-mail.

**Passos:**
1. Acessar login.
2. Informar e-mail `aluno_unifei`.
3. Informar senha válida.
4. Clicar em **Entrar**.

**Resultado esperado:**  
- Exibir “E-mail inválido”.

---

### **CT-05 – Login com usuário não cadastrado**
**Objetivo:** Verificar mensagem para usuário inexistente.

**Pré-condição:**  
- E-mail não existe na base.

**Passos:**
1. Acessar login.
2. Informar `naocadastrado@unifei.edu.br`.
3. Informar qualquer senha.
4. Clicar em **Entrar**.

**Resultado esperado:**  
- Mostrar: “Usuário não encontrado” ou “E-mail ou senha inválidos”.

---

# 🧾 Cadastro (5 Casos)

---

### **CT-06 – Cadastro com todos os campos válidos**
**Módulo:** Cadastro  
**Objetivo:** Validar cadastro completo.

**Passos:**
1. Acessar cadastro.
2. Preencher Nome, E-mail `novo@unifei.edu.br`, Senha `Senha123`, Confirmar Senha `Senha123`.
3. Aceitar termos.
4. Clicar em **Cadastrar**.

**Resultado esperado:**  
- Mensagem “Cadastro realizado com sucesso”.

---

### **CT-07 – Cadastro com e-mail já cadastrado**
**Objetivo:** Validar tratamento para e-mail duplicado.

**Pré-condição:**  
- `aluno@unifei.edu.br` já existe.

**Passos:**
1. Acessar cadastro.
2. Preencher dados com `aluno@unifei.edu.br`.
3. Clicar em **Cadastrar**.

**Resultado esperado:**  
- Exibir “E-mail já cadastrado”.

---

### **CT-08 – Cadastro com senhas diferentes**
**Objetivo:** Validar confirmação de senha.

**Passos:**
1. Acessar cadastro.
2. Informar senha `Senha123`.
3. Informar confirmação `Senha456`.
4. Clicar em **Cadastrar**.

**Resultado esperado:**  
- Exibir “As senhas não conferem”.

---

### **CT-09 – Cadastro com senha fraca**
**Objetivo:** Validar regras de senha.

**Passos:**
1. Acessar cadastro.
2. Informar senha `123`.
3. Confirmar senha `123`.
4. Clicar em **Cadastrar**.

**Resultado esperado:**  
- Exibir mensagem: “A senha deve ter no mínimo 8 caracteres”.

---

### **CT-10 – Cadastro com campos obrigatórios em branco**
**Objetivo:** Validar obrigatoriedade dos campos.

**Passos:**
1. Acessar cadastro.
2. Deixar campo obrigatório em branco.
3. Clicar em **Cadastrar**.

**Resultado esperado:**  
- Exibir “Preencha os campos obrigatórios”.

---

# 🛒 Checkout (5 Casos)

---

### **CT-11 – Checkout com dados válidos**
**Módulo:** Checkout  
**Objetivo:** Validar finalização de compra.

**Pré-condições:**
- Usuário logado.
- Carrinho com itens.

**Passos:**
1. Acessar carrinho.
2. Clicar “Finalizar compra”.
3. Informar endereço válido.
4. Selecionar método de pagamento.
5. Confirmar pedido.

**Resultado esperado:**  
- Pedido criado.  
- Exibir “Compra realizada com sucesso”.

---

### **CT-12 – Checkout com carrinho vazio**
**Objetivo:** Impedir checkout sem itens.

**Passos:**
1. Acessar carrinho vazio.
2. Clicar em “Finalizar compra”.

**Resultado esperado:**  
- Exibir “Seu carrinho está vazio”.

---

### **CT-13 – Checkout sem endereço**
**Objetivo:** Validar endereço obrigatório.

**Pré-condição:**  
- Carrinho com itens.

**Passos:**
1. Iniciar checkout.
2. Deixar endereço em branco.
3. Confirmar pedido.

**Resultado esperado:**  
- Exibir “Endereço é obrigatório”.

---

### **CT-14 – Cartão de crédito inválido**
**Objetivo:** Validar dados do cartão.

**Pré-condição:**  
- Carrinho com itens.

**Passos:**
1. Iniciar checkout.
2. Selecionar cartão.
3. Inserir `1111 1111 1111 1111`.
4. Confirmar pagamento.

**Resultado esperado:**  
- Exibir “Cartão inválido”.

---

### **CT-15 – Recalcular total ao alterar quantidade**
**Objetivo:** Validar atualização do total.

**Pré-condição:**  
- Carrinho com itens.

**Passos:**
1. Iniciar checkout.
2. Alterar quantidade para 3.
3. Verificar total.

**Resultado esperado:**  
- Total atualizado corretamente.

---

# 2) Bug Reports Profissionais (5)

---

## **BUG-01 – Checkout permite finalizar compra com carrinho vazio**
**Severidade:** Alta  
**Prioridade:** Alta  

**Ambiente:**  
- Chrome 142 – Windows 10  
- Versão 1.0.0 (produção)

**Pré-condições:**  
- Usuário logado.

**Passos:**
1. Acessar carrinho.
2. Remover itens.
3. Finalizar compra.
4. Confirmar pedido.

**Resultado atual:**  
- Pedido criado com subtotal R$0,00.

**Resultado esperado:**  
- Exibir “Seu carrinho está vazio”.

---

## **BUG-02 – Login sem mensagem de erro com credenciais inválidas**
**Severidade:** Média  
**Prioridade:** Alta  

**Ambiente:** Firefox 132 – Windows 10  

**Passos:**
1. Acessar `/login`.
2. Informar `naoexiste@unifei.edu.br`.
3. Informar `SenhaQualquer`.
4. Clicar **Entrar**.

**Resultado atual:**  
- Página recarrega sem mensagem.

**Resultado esperado:**  
- Mostrar “E-mail ou senha inválidos”.

---

## **BUG-03 – Cadastro aceita senha menor que o mínimo**
**Severidade:** Média  
**Prioridade:** Média  

**Ambiente:** Edge – Windows 11  

**Passos:**
1. Acessar cadastro.
2. Informar senha `123`.
3. Confirmar `123`.
4. Cadastrar.

**Resultado atual:**  
- Cadastro realizado.

**Resultado esperado:**  
- Exibir regra de senha mínima.

---

## **BUG-04 – Total do pedido não atualiza ao alterar quantidade**
**Severidade:** Alta  
**Prioridade:** Alta  

**Ambiente:** Chrome 142 – Windows 10  

**Passos:**
1. Acessar carrinho.
2. Visualizar total.
3. Alterar quantidade para 3.

**Resultado atual:**  
- Total não muda.

**Resultado esperado:**  
- Total recalculado.

---

## **BUG-05 – Campos apagados após erro no cadastro**
**Severidade:** Baixa  
**Prioridade:** Média  

**Ambiente:** Firefox 132 – Ubuntu 22.04  

**Passos:**
1. Preencher cadastro corretamente.
2. Informar confirmação de senha errada.
3. Clicar **Cadastrar**.
4. Corrigir senha.

**Resultado atual:**  
- Todos os campos são limpos.

**Resultado esperado:**  
- Apenas o campo inválido deve ser ajustado.

