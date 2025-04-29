# exercicio-aula-2

```sql
-- Criação das tabelas
CREATE TABLE alunos (
  id SERIAL PRIMARY KEY,
  nome TEXT NOT NULL,
  turma TEXT NOT NULL,
  curso TEXT NOT NULL,
  data_nascimento DATE
);

CREATE TABLE cursos (
  id SERIAL PRIMARY KEY,
  nome TEXT NOT NULL,
  duracao_anos INT
);

CREATE TABLE matriculas (
  id SERIAL PRIMARY KEY,
  aluno_id INT REFERENCES alunos(id) ON DELETE CASCADE,
  curso_id INT REFERENCES cursos(id) ON DELETE CASCADE,
  data_matricula DATE DEFAULT CURRENT_DATE
);

-- Inserção de alunos
INSERT INTO alunos (nome, turma, curso, data_nascimento) 
VALUES 
  ('Ana Souza', 'T18', 'Engenharia da Computação', '2005-12-03'),
  ('Bruno Lima', 'T18', 'Engenharia da Computação', '2007-03-19'),
  ('Carla Mendes', 'T18', 'Engenharia da Computação', '2005-09-09'),
  ('Diego Alves', 'T18', 'Engenharia da Computação', '2001-08-23'),
  ('Eduarda Silva', 'T18', 'Sistema da Informação', '2003-01-17'),
  ('Felipe Torres', 'T18', 'Sistema da Informação', '2002-11-30'),
  ('Gustavo Rocha', 'T18', 'Engenharia de Software', '2001-06-04'),
  ('Helena Castro', 'T18', 'Engenharia de Software', '2002-09-12'),
  ('Igor Martins', 'T18', 'Engenharia de Software', '2003-03-27'),
  ('Juliana Freitas', 'T18', 'Engenharia de Software', '2001-12-05');

-- Inserção de cursos
INSERT INTO cursos (nome, duracao_anos)
VALUES 
  ('Engenharia da Computação', 5),
  ('Engenharia de Software', 5),
  ('Sistema da Informação', 4);

-- Inserção de matrículas
INSERT INTO matriculas (aluno_id, curso_id)
VALUES 
  (1, 1),
  (9, 2),
  (5, 3);
```
