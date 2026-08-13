Sistema Escolar
Sobre o Projeto:
Esse projeto foi feio como uma atividade para criar um sistema escolar simples, onde o aluno consegue acessar algumas informações escolares.
O sistema foi feito usando HTML, CSS e JavaScript. A ideia foi criar uma página onde é possível fazer login, consultar notas, verificar frequência e pegar livros da biblioteca.

Funcionalidades
O sistema possui algumas funcionalidades principais:
Login do aluno
Página inicial
Consulta de notas
Consulta de frequência
Justificativa de faltas
Empréstimo de livros
Devolução de livros
Validação de informações digitadas pelo usuári
Tratamento de erros

Tecnologias Usadas
Para fazer o projeto foram utilizadas
HTML
CSS
JavaScript
GitHub

Estrutura Do projeto
O projeto possui os seguintes arquivos

sistema-escolar
login.html
inicio.html
notas.html
frequencia.html
biblioteca.html

Login.html
É a tela onde o aluno faz o login para entrar no sistema.
Nessa página são verificadas algumas informações, como o e-mail e a senha.
O sistema verifica se o e-mail possui o formato esperado e também verifica se a senha foi preenchida corretamente.
Por exemplo, se o usuário colocar:
Aluno
no campo de e-mail, o sistema informa que o formato está incorreto. Um exemplo de e-mail válido para o sistema seria:
sthefany@escola.pr.gov.br

Inicio.html
É a página principal do sistema.Nela o aluno consegue acessar as outras partes do sistema, como notas, frequência e biblioteca.

Notas.html
Nessa página o aluno consegue consultar suas notas antes de mostrar as notas, o sistema pede uma senha. Se a senha estiver errada ou tiver poucos caracteres,
uma mensagem de erro é mostrada.

Frequencia.html
Essa página mostra a frequência do aluno nas matérias, também existe uma opção para justificar uma falta
o sistema verifica se a justificativa foi preenchida corretamente antes de aceitar.

biblioteca.html

Nessa parte é possível simular o empréstimo e a devolução de livros, o sistema também verifica se existe algum livro que ainda não foi devolvido antes de permitir um novo empréstimo.

testes unitários
Foram feitos 5 testes unitários para verificar algumas funções do sistema.
os testes estão no arquivo `notas.html` e utilizam uma função `assert` para verificar se o resultado esperado está sendo retornado.

teste 1 - senha curta
Esse teste verifica se o sistema identifica uma senha com menos de 6 caracteres.
Exemplo:

123

O resultado esperado é que o sistema informe que a senha é muito curta.

Teste 2 - senha incorreta
Nesse teste é utilizada uma senha diferente da senha cadastrada.
Exemplo:

sthefane

O resultado esperado é que o sistema informe que a senha está incorreta.

Teste 3 - Senha Curta

Nesse teste é utilizada a senha correta:

sthefany

O resultado esperado é que a senha seja aceita.

Teste 4 - Texto muito curto
Esse teste verifica se um texto possui pelo menos 6 caracteres.

Exemplo:

abc

O resultado esperado é:

 texto curto

Teste 5 - tamanho de texto suficiente
Nesse teste é utilizado um texto com 6 ou mais caracteres.

Exemplo:

sthefany

O resultado esperado é:
OK

Tratamento de exceções 
O sistema possui algumas verificações para evitar que informações erradas causem problemas.
No JavaScript foram utilizados `try`, `catch` e `throw new Error()` para tratar esses casos.
Por exemplo, na página de notas, antes de liberar o acesso ao boletim, a senha é verificada.
Se a senha tiver poucos caracteres, o sistema mostra uma mensagem informando o problema.
Se a senha estiver errada, também é mostrada uma mensagem para o usuário.
Isso faz com que o sistema consiga lidar com entradas incorretas sem simplesmente parar de funcionar.

exemplo de validação de login
O campo de e-mail possui uma validação para verificar se o usuário colocou um e-mail com o domínio esperado.

Por exemplo:

Aluno

não é aceito porque não possui um formato de e-mail.
Já:

sthefany@escola.pr.gov.br

possui o formato esperado pelo sistema.
A senha também é verificada antes de permitir o acesso.

Clean Code
Tentei deixar o código mais organizado e fácil de entender.
Algumas coisas utilizadas foram:
Nomes de funções que explicam o que elas fazem
Separação das funcionalidades em diferentes páginas
Funções para realizar as validações
Mensagens de erro para ajudar o usuário;
Uso de `const` e `let`;
Evitar código repetido quando possível.

Algumas funções utilizadas no projeto são:
javascript
processarValidaSenha()

javascript
analisarTextoJustificativa()

javascript
verificarStatusFisicoNaBiblioteca()

javascript
verificarPermissaoNovoEmprestimo()

Os nomes ajudam a entender qual é a função de cada uma delas.

Refatoração
Uma das partes que foi refatorada foi a função responsável por verificar o tamanho de um texto.
Uma forma mais comprida poderia ser feita assim:

javascript
function verificarTamanho(str) {
    if (str.length >= 6) {
        return "OK";
    } else {
        return "Curto";
    }
}

Deixei ela foi deixada de uma forma mais curta:

javascript
const validaTamanhoCurto = (str) =>
    str.length >= 6 ? "OK" : "Curto";

O resultado continua sendo o mesmo, mas a segunda versão possui menos código e fica mais simples para uma validação desse tipo.
Essa função também é utilizada nos testes unitários.
