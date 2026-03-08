
[casos-de-teste.md](https://github.com/user-attachments/files/25827118/casos-de-teste.md)
# 📋 Portfólio de Casos de Teste — QA Studies

Repositório de estudos em Quality Assurance com casos de teste manuais criados em sites de prática como Swag Labs, Demoblaze e The Internet.

---

## Sumário

| ID | Título | Módulo | Prioridade |
|---|---|---|---|
| TC001 | Login com credenciais válidas no Mercado Livre | Autenticação | Alta |
| TC002 | Finalizar compra com sucesso no Swag Labs | Checkout / Pagamento | Alta |
| TC003 | Verificar exibição de notificação ao clicar no botão "Click here" | Notification Messages | Baixa |
| TC004 | Login com credenciais inválidas no Swag Labs | Autenticação | Alta |
| TC005 | Tentar finalizar pedido com informações inválidas no Demoblaze | Pagamento | Alta |
| TC006 | Login com campos em branco no Swag Labs | Autenticação | Alta |
| TC007 | Finalizar checkout com campos em branco no Swag Labs | Pagamento | Alta |
| TC008 | Remover produto do carrinho antes de finalizar no Swag Labs | Carrinho | Média |
| TC009 | Ordenar produtos por preço menor ao maior no Swag Labs | Filtros | Média |
| TC010 | Login com usuário bloqueado no Swag Labs | Autenticação | Alta |

---

## TC001 — Login com credenciais válidas no Mercado Livre

**Módulo:** Autenticação
**Prioridade:** Alta
**Tipo:** Positivo

**Pré-condições:**
- Navegador aberto (Chrome/Firefox)
- Acesso a www.mercadolivre.com.br
- Conta já cadastrada

**Passos:**
1. Acessar www.mercadolivre.com.br
2. Clicar em **Entre/Registre-se** no canto superior direito
3. Clicar na aba **Entrar com e-mail**
4. Preencher o campo **E-mail** com `teste@exemplo.com`
5. Preencher o campo **Senha** com `Senha123`
6. Clicar no botão **Entrar**

**Resultado Esperado:**
- O usuário é redirecionado para a página inicial
- O nome do usuário é exibido no canto superior direito
- O menu **Minhas compras** está acessível
- A página inicial personalizada é carregada

**Dados de Teste:**
- E-mail: `teste@exemplo.com`
- Senha: `Senha123`

---

## TC002 — Finalizar compra com sucesso no Swag Labs

**Módulo:** Checkout / Pagamento
**Prioridade:** Alta
**Tipo:** Positivo

**Pré-condições:**
- Navegador aberto
- Acesso a www.saucedemo.com
- Conta já cadastrada

**Passos:**
1. Acessar www.saucedemo.com
2. Inserir `standard_user` no campo **Username**
3. Inserir `secret_sauce` no campo **Password**
4. Clicar no botão **Login**
5. Selecionar um produto e clicar em **Add to cart**
6. Clicar no ícone do carrinho no canto superior direito
7. Verificar se o produto está listado no carrinho
8. Clicar em **Checkout**
9. Preencher o campo **First Name** com um nome válido
10. Preencher o campo **Last Name** com um sobrenome válido
11. Preencher o campo **Zip/Postal Code** com um CEP válido
12. Clicar em **Continue**
13. Verificar o resumo do pedido na tela de Overview
14. Clicar em **Finish**

**Resultado Esperado:**
- A página de confirmação é exibida
- A mensagem **"Thank you for your order!"** aparece na tela
- O carrinho fica vazio após a finalização

**Dados de Teste:**
- Username: `standard_user`
- Password: `secret_sauce`
- First Name: `João`
- Last Name: `Silva`
- Postal Code: `01310-100`

---

## TC003 — Verificar exibição de notificação ao clicar no botão "Click here"

**Módulo:** Notification Messages
**Prioridade:** Baixa
**Tipo:** Positivo

**Pré-condições:**
- Navegador aberto
- Acesso a https://the-internet.herokuapp.com

**Passos:**
1. Acessar https://the-internet.herokuapp.com
2. Localizar e clicar em **Notification Messages** na lista da página inicial
3. Verificar se a página de Notification Messages foi carregada corretamente
4. Clicar no botão **Click here**
5. Verificar se uma mensagem de notificação aparece no topo da página

**Resultado Esperado:**
- Uma mensagem de notificação é exibida no topo da página após o clique
- A mensagem pode variar entre *"Action successful"* ou *"Action unsuccessful, please try again"*
- A notificação some automaticamente após alguns segundos ou pode ser fechada manualmente

**Dados de Teste:**
- N/A

---

## TC004 — Login com credenciais inválidas no Swag Labs

**Módulo:** Autenticação
**Prioridade:** Alta
**Tipo:** Negativo

**Pré-condições:**
- Navegador aberto
- Acesso a www.saucedemo.com

**Passos:**
1. Acessar www.saucedemo.com
2. Inserir um username inválido no campo **Username**
3. Inserir uma senha inválida no campo **Password**
4. Clicar no botão **Login**

**Resultado Esperado:**
- O usuário não é redirecionado para a página de produtos
- O usuário permanece na página de login
- A mensagem de erro é exibida: *"Username and password do not match any user in this service"*

**Dados de Teste:**
- Username: `teste`
- Password: `123456`

---

## TC005 — Tentar finalizar pedido com informações inválidas no Demoblaze

**Módulo:** Pagamento
**Prioridade:** Alta
**Tipo:** Negativo

**Pré-condições:**
- Navegador aberto
- Acesso a www.demoblaze.com
- Conta já cadastrada

**Passos:**
1. Acessar www.demoblaze.com
2. Clicar em **Log in** no canto superior direito
3. Inserir username no campo **Username**
4. Inserir senha no campo **Password**
5. Clicar em **Log in**
6. Selecionar um produto e clicar em **Add to cart**
7. Clicar no ícone do carrinho na parte superior
8. Clicar no botão **Place Order**
9. Preencher o campo **Name** com `asfgfa`
10. Preencher o campo **Country** com `aaaa`
11. Preencher o campo **City** com `bbbb`
12. Preencher o campo **Credit Card** com `1234`
13. Preencher o campo **Month** com `a12d`
14. Preencher o campo **Year** com `20000`
15. Clicar em **Purchase**

**Resultado Esperado:**
- O sistema exibe mensagem de confirmação de compra mesmo com dados inválidos
- ⚠️ **Bug identificado:** O sistema não valida os campos do checkout, permitindo finalizar compras com dados completamente inválidos

**Dados de Teste:**
- Username: `Ameixa`
- Password: `123456`
- Name: `asfgfa`
- Country: `aaaa`
- City: `bbbb`
- Credit Card: `1234`
- Month: `a12d`
- Year: `20000`

---

## TC006 — Login com campos em branco no Swag Labs

**Módulo:** Autenticação
**Prioridade:** Alta
**Tipo:** Negativo

**Pré-condições:**
- Navegador aberto
- Acesso a www.saucedemo.com

**Passos:**
1. Acessar www.saucedemo.com
2. Deixar o campo **Username** em branco
3. Deixar o campo **Password** em branco
4. Clicar no botão **Login**

**Resultado Esperado:**
- O usuário não é redirecionado para a página de produtos
- O usuário permanece na página de login
- A mensagem de erro é exibida: *"Epic sadface: Username is required"*

**Dados de Teste:**
- N/A

---

## TC007 — Finalizar checkout com campos em branco no Swag Labs

**Módulo:** Pagamento
**Prioridade:** Alta
**Tipo:** Negativo

**Pré-condições:**
- Navegador aberto
- Acesso a www.saucedemo.com
- Conta já cadastrada

**Passos:**
1. Inserir `standard_user` no campo **Username**
2. Inserir `secret_sauce` no campo **Password**
3. Clicar no botão **Login**
4. Selecionar um produto e clicar em **Add to cart**
5. Clicar no ícone do carrinho no canto superior direito
6. Clicar no botão **Checkout**
7. Deixar o campo **First Name** em branco
8. Deixar o campo **Last Name** em branco
9. Deixar o campo **Zip/Postal Code** em branco
10. Clicar no botão **Continue**

**Resultado Esperado:**
- O usuário não avança para a próxima etapa do checkout
- O usuário permanece na página de informações do checkout
- A mensagem de erro é exibida: *"Error: First Name is required"*

**Dados de Teste:**
- Username: `standard_user`
- Password: `secret_sauce`

---

## TC008 — Remover produto do carrinho antes de finalizar no Swag Labs

**Módulo:** Carrinho
**Prioridade:** Média
**Tipo:** Positivo

**Pré-condições:**
- Navegador aberto
- Acesso a www.saucedemo.com
- Conta já cadastrada

**Passos:**
1. Inserir `standard_user` no campo **Username**
2. Inserir `secret_sauce` no campo **Password**
3. Clicar no botão **Login**
4. Selecionar um produto e clicar em **Add to cart**
5. Clicar no ícone do carrinho no canto superior direito
6. Localizar o produto adicionado na lista do carrinho
7. Clicar no botão **Remove** do produto

**Resultado Esperado:**
- O produto é removido da lista do carrinho
- A lista do carrinho fica vazia
- O contador do ícone do carrinho no canto superior direito desaparece
- O usuário permanece na página do carrinho

**Dados de Teste:**
- Username: `standard_user`
- Password: `secret_sauce`

---

## TC009 — Ordenar produtos por preço menor ao maior no Swag Labs

**Módulo:** Filtros
**Prioridade:** Média
**Tipo:** Positivo

**Pré-condições:**
- Navegador aberto
- Acesso a www.saucedemo.com
- Conta já cadastrada

**Passos:**
1. Inserir `standard_user` no campo **Username**
2. Inserir `secret_sauce` no campo **Password**
3. Clicar no botão **Login**
4. Localizar o menu de filtro no canto superior direito abaixo do ícone do carrinho
5. Clicar no menu de filtro
6. Selecionar a opção **Price (low to high)**

**Resultado Esperado:**
- Os produtos são reordenados na mesma página
- O primeiro produto da lista é o de menor preço
- O último produto da lista é o de maior preço
- Nenhum produto some ou é adicionado após a ordenação

**Dados de Teste:**
- Username: `standard_user`
- Password: `secret_sauce`

---

## TC010 — Login com usuário bloqueado no Swag Labs

**Módulo:** Autenticação
**Prioridade:** Alta
**Tipo:** Negativo

**Pré-condições:**
- Navegador aberto
- Acesso a www.saucedemo.com

**Passos:**
1. Inserir `locked_out_user` no campo **Username**
2. Inserir `secret_sauce` no campo **Password**
3. Clicar no botão **Login**

**Resultado Esperado:**
- O usuário não é redirecionado para a página de produtos
- O usuário permanece na página de login
- A mensagem de erro é exibida: *"Epic sadface: Sorry, this user has been locked out"*

**Dados de Teste:**
- Username: `locked_out_user`
- Password: `secret_sauce`
