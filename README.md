1️⃣ Funcionalidade: Registro de Usuários (Professor/Aluno)

User Story:

Como usuário (aluno ou professor)
Eu quero me registrar no sistema
Para que eu possa acessar e utilizar as funcionalidades de gestão de cursos e alunos

Regras de Negócio:

O e-mail deve ser único (não pode haver dois usuários com o mesmo e-mail).

O campo tipo de usuário deve ser obrigatório e aceitar apenas os valores: "aluno" ou "professor".

A senha deve ter no mínimo 8 caracteres.

O sistema deve validar todos os campos obrigatórios antes de concluir o registro.

Apenas professores podem criar e gerenciar cursos.

Um token JWT deve ser gerado após o registro bem-sucedido.

🔐 2️⃣ Funcionalidade: Login de Usuários (Professor/Aluno)

User Story:

Como usuário (aluno ou professor)
Eu quero fazer login no sistema
Para que eu possa acessar os recursos conforme o meu perfil

Regras de Negócio:

O login deve exigir e-mail e senha válidos.

Se o e-mail ou a senha estiver incorreto, o sistema deve retornar erro 401 - Unauthorized.

Após o login bem-sucedido, o sistema deve gerar e retornar um token JWT com a função do usuário (aluno/professor).

O token deve ser obrigatório para acessar qualquer endpoint protegido (cursos, alunos, etc.).

Tokens expirados devem ser invalidados automaticamente.

📚 3️⃣ Funcionalidade: Gestão de Cursos de Idiomas

User Story:

Como professor
Eu quero criar, atualizar e listar cursos de idiomas
Para que os alunos possam se inscrever e participar desses cursos

Regras de Negócio:

Apenas usuários com perfil de professor podem criar, editar ou excluir cursos.

Cada curso deve conter os campos: nome, idioma, nível e descrição.

Não pode haver dois cursos com o mesmo nome e idioma.

Professores podem listar apenas os cursos que criaram.

Alunos podem visualizar todos os cursos disponíveis.

Cursos não podem ser deletados se houver alunos matriculados.

🎓 4️⃣ Funcionalidade: Listar Alunos

User Story:

Como professor
Eu quero listar todos os alunos cadastrados e seus respectivos cursos
Para que eu possa acompanhar o progresso e as matrículas dos alunos

Regras de Negócio:

Apenas professores podem visualizar a lista completa de alunos.

Cada aluno deve estar associado a pelo menos um curso.

Os alunos devem poder visualizar apenas o próprio perfil e curso.

Professores podem filtrar alunos por curso ou idioma.

A resposta deve exibir: nome do aluno, curso, idioma e status da matrícula.