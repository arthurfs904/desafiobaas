## BUG #01 — [Entrar]

### O que estava acontecendo
O login mesmo com usuario e senha incorretos travava ao clicar no botao para entrar nao validando os dados

### Por que acontecia
Linha 32 e 33, função catch estava vazio sem o tratamento do erro retornado pelo firebase
### Como corrigi
antes:
} catch {
  // catch vazio: o erro é silenciado.
depois:
} catch (err) {
  setErro("E-mail ou senha inválidos.");

### Screenshot ou resultado

## BUG #03 — [Senhas nao coincidem]

### O que estava acontecendo
Mesmo que as senhas sejam iguais o sistema nao consegue validar

### Por que acontecia
cadastro/page.tsx linha 32, o codigo estava comparando senha com nome ao inves de comparar senha e confirmação de senha
### Como corrigi
antes:
if (senha !== nome) {
depois:
if (senha !== confirmarSenha) {

### Screenshot ou resultado
[Print da tela com o bug funcionando ERRADO e depois funcionando CERTO]