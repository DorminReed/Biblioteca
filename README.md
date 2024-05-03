# Biblioteca

Create DATABASE anangueraAtividade;
USE anangueraAtividade;

Create TABLE aluno (
Ra INT PRIMARY KEY AUTO_INCREMENT,
Nome VARCHAR(50) NOT NULL,
Email VARCHAR(50) NOT NULL,
Telefone VARCHAR(50) NOT NULL
);

Create TABLE livro (
Isbn INT PRIMARY KEY AUTO_INCREMENT,
Nome VARCHAR(50) NOT NULL,
Autor VARCHAR(50) NOT NULL,
Páginas INT,
FOREIGN KEY (Isbn) REFERENCES aluno(Ra)
);

Create TABLE colaborador(
Cpf INT PRIMARY KEY AUTO_INCREMENT,
Nome VARCHAR(50) NOT NULL,
Email VARCHAR(50) NOT NULL,
Cargo VARCHAR(50) NOT NULL
);

Create TABLE empréstimo(
Id INT PRIMARY KEY AUTO_INCREMENT,
DataEmprestimo DATE,
DataDevolucao DATE,
LivrosIsbn INT,
ColaboradorCpf INT,
FOREIGN KEY (LivrosIsbn) REFERENCES livro(Isbn),
FOREIGN KEY (ColaboradorCpf) REFERENCES colaborador(Cpf)
);
