# Prova1
Sistema para gerenciamento de projetos

# Funcionalidades
Login e Logout
  
    O usuário entra no sistema mediante a inserção de login e senha. Checa-se se ele é um usuário 
    cadastrado e se é a senha correta. Isto é feito pelo método login na classe sistema, que possui tratamento de exceção 
    para dados errados informados pelo usuário. O usuário sai do sistema através do método logout, que quebra o loop do usuario 
    e retorna ao menu inicial.
    
Buscas

    Através dos métodos user_search, project_search, atividade_search, da classe sistema, obtém-se informações sobre usuários, 
    projetos e atividades, respectivamente. Cada um deles invoca seu respectivo método de informação. 
    Todos eles possuem tratamento de exceção para dados errados informados pelo usuário.
    
Adição e edição de projetos

    Usuários que sejam professores ou pesquisadores e coordenadores, podem adicionar projetos e editar projetos dos quais sejam 
    os coordenadores, através do metodo add_project, da  classe coordenador. Edições são feitas pelo método edit_info, da 
    classe projeto. Todos eles possuem tratamento de exceção para dados errados informados pelo usuário.
    
Adição de e edição atividades

    Tem os mesmos requisitos da funcionalidade anterior e tem explicação análoga. É feita pelo método add_atividade da classe 
    projeto, e editada pelao metodo edit_info, da classe atividade. Com tratamento de exceções.
    
Adição e edição de usuário

    No menu inicial, através do método new_user, da classe sistema. Um novo usuário é adicionado a lista de usuarios do 
    sistema. Após efetuado o login, as informações do próprio usuário, nunca de terceiros, pode ser alterada pelo método
    edit_user, da classe pessoa.
    
Relatório do Sistema

    Através do método index, da classe sistema, um relatório é exposto ao usuário, o método index chama os métodos de
    informação para cada projeto, pessoa e atividade registrada no sistema.
    
# Classes

Projeto
    
    Possui Strings para descrição, status e titulo do projeto. Inteiros com o indice na lista de projetos do sistema (id), 
    com data e hora de inicio e fim e salvando o login do coordenador, tem de ser um professor ou um pesquisador. 
    Tem uma lista salvando os logins dos participantes do projeto, qualquer cargo pode participar do projeto.
    Por fim, tem um lista de atividades, que salva todas as 
    atividades relacionadas ao projeto. Esta classe foi feita para representar um projeto e tudo que ele possui.
    
Atividade

    Possui inteiros com data e hora de inicio e fim e salvando o login do responsável, tem que ser algum profissional 
    (desenvolvedor, testador ou analista). Tem uma lista salvando os logins dos participantes do projeto, só são permitidos 
    profissionais. E uma lista de strings, que salva a descrição da tarefa do profissional na posição com indice igual ao do
    profissional. Foi feita para representar e separar as atividades dos projetos.
    
Pessoa

    Possui inteiros com id e cpf. Strings com nome, tipo (graduação, mestrado, professor, testador...), nome e senha. Também
    possui uma lista de inteiros com os ids dos projetos que a pessoa participa. Foi criada para representar um usuário 
    genérico.
    
Coordenador

    Herdeira de Pessoa, tem a mais um booleano que diz se esse usuário é ou não coordenador, o tipo tem de ser professor ou 
    pesquisador. Foi criada para separar os coordenadores de usuários comuns,  também tem o poder de criar um projeto, desde
    que o booleano citado seja verdadeiro.
    
Reg

    Possui dois inteiros, um que salva o id do projeto e o que salva o id da atividade. Foi criada para servir de registrador 
    e servir como uma matriz de inteiros, quando se faz uma lista com ela.
    
Profissional

    Herdeira de Pessoa, tem uma lista de reg para gerenciar as atividades que os profissionais participam, o tipo tem de ser
    analista, desenvolvedor ou testador.
    
Sistema

    Possui uma lista de pessoas e uma lista de projetos. Serve justamente para isso, para unir as pessoas com os projetos, 
    também contém os métodos que tratam diretamente com o usuário.
    
# Distribuição dos métodos

Os métodos que precisam de contato direto com o usuário foram concentrados na classe sistema, para evitar que várias partes 
do código fossem acessadas pelo usuário. Os outros métodos  ficam distribuídos nas classes que eles atuam, por questões de 
organização. Os métodos que alteram dados de projeto ficam na classe projeto, e assim sucessivamente.

# Tratamento de exceções

Todos os métodos que precisam de contato direto com o usuário, possuem tratamento de exceção para dados errados informados 
pelo umesmo.

# Herança

Se deu nas classes Pessoa, Coordenador e Profissional e foi destrinchada nas explicações delas.

# Reuso

Se deu nos métodos de informação que podem ser chamados tanto diretamente pelo usuário, quanto pelos métodos de busca e do 
relatório do sistema

