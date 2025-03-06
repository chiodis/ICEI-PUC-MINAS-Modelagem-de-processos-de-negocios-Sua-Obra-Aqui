## Arquivo .sql  SUA OBRA AQUI!

CREATE DATABASE IF NOT EXISTS dbSuaObraAqui;

USE dbSuaObraAqui;

-- Tabela usuarios
CREATE TABLE IF NOT EXISTS  usuarios (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    email VARCHAR(100) NOT NULL UNIQUE,
    senha VARCHAR(255) NOT NULL,
    tipo_perfil ENUM('cliente', 'profissional') NOT NULL, 
    validacao_sms BOOLEAN DEFAULT FALSE,
    codigo_sms VARCHAR(6) DEFAULT NULL,
    data_criacao TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Inserção de dados na tabela usuarios
INSERT INTO usuarios (nome, email, senha, tipo_perfil, validacao_sms, codigo_sms)
VALUES
 ('Ava', 'ava@gmail.com', SHA2('senha123', 256), 'cliente', FALSE, '123456'),
('Evelyn', 'evelyn@gmail.com', SHA2('senha456', 256), 'cliente', TRUE, NULL),
('Emily', 'emily@gmail.com', SHA2('senha789', 256), 'cliente', FALSE, '654321'),
('Grace', 'grace@gmail.com', SHA2('senhaabc', 256), 'cliente', TRUE, NULL),
('Chloe', 'chloe@gmail.com', SHA2('senhadef', 256), 'cliente', FALSE, '789654'),
('Liam', 'liam@gmail.com', SHA2('senha321', 256), 'cliente', TRUE, NULL),
('Noah', 'noah@gmail.com', SHA2('senha654', 256), 'cliente', FALSE, '456789'),
('Elijah', 'elijah@gmail.com', SHA2('senhaghi', 256), 'cliente', TRUE, NULL),
('Logan', 'logan@gmail.com', SHA2('senhajkl', 256), 'cliente', FALSE, '987123'),
('Jacob', 'jacob@gmail.com', SHA2('senhamno', 256), 'cliente', TRUE, NULL),
('Leon', 'leon@gmail.com', SHA2('senhapqr', 256), 'profissional', FALSE, '456321'),
('Felix', 'felix@gmail.com', SHA2('senhastu', 256), 'profissional', TRUE, NULL),
('Yusuf', 'yusuf@gmail.com', SHA2('senhavwx', 256), 'profissional', FALSE, '123987'),
('Ivan', 'ivan@gmail.com', SHA2('senhayza', 256), 'profissional', TRUE, NULL),
('Alexander', 'alexander@gmail.com', SHA2('senhabcd', 256), 'profissional', FALSE, '741852'),
('Théo', 'theo@gmail.com', SHA2('senhadefg', 256), 'profissional', TRUE, NULL),
('Dmitry', 'dmitry@gmail.com', SHA2('senhahij', 256), 'profissional', TRUE, NULL),
('Vicent', 'vicent@gmail.com', SHA2('senhaklm', 256), 'profissional', FALSE, '963258'),
('Jade', 'jade@gmail.com', SHA2('senhanop', 256), 'profissional', TRUE, NULL),
('Azra', 'azra@gmail.com', SHA2('senhaqrs', 256), 'profissional', FALSE, '159357'),
('Alisa', 'alisa@gmail.com', SHA2('senhatuv', 256), 'profissional', TRUE, NULL),
('Daria', 'daria@gmail.com', SHA2('senhawxy', 256), 'profissional', FALSE, '753951');

-- Tabela cadastro_usuario
CREATE TABLE IF NOT EXISTS cadastro_usuario(
    id_cadastro INT AUTO_INCREMENT PRIMARY KEY, 
    id_usuario INT NOT NULL,                     
    data_cadastro TIMESTAMP DEFAULT CURRENT_TIMESTAMP,  
    FOREIGN KEY (id_usuario) REFERENCES usuarios(id)    
);

-- Inserção de dados na tabela cadastro_usuario
INSERT INTO cadastro_usuario (id_usuario)
VALUES 
(1), (2), (3), (4), (5), 
(6), (7), (8), (9), (10), 
(11), (12), (13), (14), (15), 
(16), (17), (18), (19), (20),
(21), (22);

-- Tabela FAQs
CREATE TABLE IF NOT EXISTS FAQs (
    id_faq INT AUTO_INCREMENT PRIMARY KEY,
    pergunta TEXT NOT NULL,
    passo_a_passo TEXT NOT NULL
);

-- Inserção de FAQs
INSERT INTO FAQs (pergunta, passo_a_passo)
VALUES
('Como faço para resetar minha senha?', '1. Clique em "Esqueci minha senha". 2. Insira seu e-mail. 3. Siga as instruções enviadas.'),
('Como atualizar meu cadastro?', '1. Faça login no site. 2. Acesse a área do cliente. 3. Clique em "Atualizar Cadastro".'),
('Como solicitar suporte técnico?', '1. Acesse a página de suporte. 2. Preencha o formulário. 3. Aguarde o contato.');

-- Tabela TentativasFAQ
CREATE TABLE IF NOT EXISTS TentativasFAQ (
    id_tentativa INT AUTO_INCREMENT PRIMARY KEY,
    id_usuario INT NOT NULL,
    id_faq INT NOT NULL,
    resultado BOOLEAN DEFAULT 0,
    data_tentativa DATETIME DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (id_usuario) REFERENCES usuarios(id),
    FOREIGN KEY (id_faq) REFERENCES FAQs(id_faq)
);

-- Inserção de TentativasFAQ
INSERT INTO TentativasFAQ (id_usuario, id_faq, resultado)
VALUES
(1, 1, TRUE),
(2, 2, FALSE),
(3, 3, FALSE);

-- Tabela SolicitacoesSuporte
CREATE TABLE IF NOT EXISTS SolicitacoesSuporte (
    id_suporte INT AUTO_INCREMENT PRIMARY KEY,
    id_usuario INT NOT NULL,
    descricao_problema TEXT NOT NULL,
    data_solicitacao DATETIME DEFAULT CURRENT_TIMESTAMP,
    status VARCHAR(50) DEFAULT 'Em análise',
    FOREIGN KEY (id_usuario) REFERENCES usuarios(id)
);

-- Inserção de dados na tabela SolicitacoesSuporte
INSERT INTO SolicitacoesSuporte (id_usuario, descricao_problema, status)
VALUES
(2, 'Não consegui atualizar meu cadastro.', 'Em análise'),
(3, 'Erro no envio do formulário de suporte.', 'Resolvido');

-- Tabela AnalisesSuporte
CREATE TABLE IF NOT EXISTS AnalisesSuporte (
    id_analise INT AUTO_INCREMENT PRIMARY KEY,
    id_suporte INT NOT NULL,
    descricao_analise TEXT NOT NULL,
    resolvido BOOLEAN DEFAULT FALSE,
    data_analise DATETIME DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (id_suporte) REFERENCES SolicitacoesSuporte(id_suporte)
);

-- Inserção de dados na tabela AnalisesSuporte
INSERT INTO AnalisesSuporte (id_suporte, descricao_analise, resolvido)
VALUES
(1, 'Problema no cadastro corrigido.', TRUE),
(2, 'Erro no formulário identificado e corrigido.', TRUE);

-- Tabela Avaliacoes
CREATE TABLE IF NOT EXISTS Avaliacoes (
    id_avaliacao INT AUTO_INCREMENT PRIMARY KEY,
    id_suporte INT NOT NULL,
    nota INT CHECK (nota BETWEEN 1 AND 5),
    comentario TEXT,
    FOREIGN KEY (id_suporte) REFERENCES SolicitacoesSuporte(id_suporte)
);

-- Inserção de dados na tabela Avaliacoes
INSERT INTO Avaliacoes (id_suporte, nota, comentario)
VALUES
(1, 4, 'Suporte rápido, mas tive que abrir chamado.'),
(2, 5, 'Ótimo atendimento, problema resolvido rapidamente.');

-- Tabela Solicitacoes
CREATE TABLE IF NOT EXISTS Solicitacoes (
    id INT AUTO_INCREMENT PRIMARY KEY,
    NomeProjeto VARCHAR(255) NOT NULL DEFAULT 'Projeto Sem Nome',
    TipoObra VARCHAR(255) NOT NULL DEFAULT 'Residencial',
    Descricao VARCHAR(255) DEFAULT 'N/A',
    AreaTotal DECIMAL(10, 2) NOT NULL DEFAULT 0.00,
    CHECK (TipoObra IN ('Residencial', 'Comercial', 'Industrial'))
);

-- Inserção de dados na tabela Solicitacoes
INSERT INTO Solicitacoes (NomeProjeto, TipoObra, Descricao, AreaTotal)
VALUES
('Projeto Alpha', 'Residencial', 'Construção de uma casa de dois andares', 150.50),
('Projeto Beta', 'Comercial', 'Construção de um pequeno galpão', 250.00),
('Projeto Gama', 'Industrial', 'Construção de uma fábrica de médio porte', 500.00),
('Projeto Delta', 'Residencial', 'Reforma de um apartamento', 80.00),
('Projeto Epsilon', 'Comercial', 'Construção de um restaurante', 120.00),
('Projeto Zeta', 'Residencial', 'Construção de uma casa moderna', 200.00),
('Projeto Eta', 'Comercial', 'Construção de uma loja de conveniência', 90.00),
('Projeto Theta', 'Industrial', 'Construção de um armazém logístico', 700.00),
('Projeto Iota', 'Residencial', 'Construção de um condomínio de luxo', 1000.00),
('Projeto Kappa', 'Comercial', 'Construção de um shopping center', 1500.00),
('Projeto Lambda', 'Industrial', 'Construção de uma usina de energia', 5000.00),
('Projeto Mu', 'Residencial', 'Reforma de uma casa térrea', 75.00),
('Projeto Nu', 'Comercial', 'Construção de um centro de distribuição', 300.00),
('Projeto Xi', 'Industrial', 'Construção de uma linha de montagem', 1200.00),
('Projeto Omicron', 'Residencial', 'Construção de uma vila residencial', 800.00),
('Projeto Pi', 'Comercial', 'Construção de um restaurante temático', 150.00),
('Projeto Rho', 'Industrial', 'Construção de um parque industrial', 2500.00),
('Projeto Sigma', 'Residencial', 'Reforma de um apartamento de luxo', 120.00),
('Projeto Tau', 'Comercial', 'Construção de um escritório corporativo', 450.00),
('Projeto Upsilon', 'Industrial', 'Construção de uma fábrica de eletrônicos', 1800.00),
('Projeto Phi', 'Residencial', 'Construção de um chalé de montanha', 90.00),
('Projeto Chi', 'Comercial', 'Construção de uma padaria artesanal', 80.00),
('Projeto Psi', 'Industrial', 'Construção de uma refinaria', 6000.00),
('Projeto Omega', 'Residencial', 'Construção de uma casa ecológica', 140.00),
('Projeto Alfa II', 'Comercial', 'Reforma de um centro comercial', 250.00),
('Projeto Beta II', 'Residencial', 'Construção de um estúdio de fotografia', 50.00),
('Projeto Gama II', 'Industrial', 'Construção de uma fábrica de cimento', 3500.00),
('Projeto Delta II', 'Comercial', 'Construção de um coworking', 200.00),
('Projeto Epsilon II', 'Residencial', 'Reforma de um sobrado', 100.00),
('Projeto Zeta II', 'Comercial', 'Construção de uma farmácia', 120.00),
('Projeto Eta II', 'Industrial', 'Construção de uma unidade fabril', 2200.00),
('Projeto Theta II', 'Residencial', 'Construção de uma cobertura de luxo', 300.00),
('Projeto Iota II', 'Comercial', 'Reforma de uma galeria de arte', 110.00),
('Projeto Kappa II', 'Industrial', 'Construção de uma central de reciclagem', 800.00),
('Projeto Lambda II', 'Residencial', 'Construção de um loft urbano', 60.00);


-- Tabela Materiais
CREATE TABLE IF NOT EXISTS Materiais (
    id INT AUTO_INCREMENT PRIMARY KEY,
    Nome VARCHAR(255) NOT NULL DEFAULT 'Material Genérico',
    Quantidade DECIMAL(10, 2) NOT NULL DEFAULT 1,
    UnidadeMedida VARCHAR(50) NOT NULL DEFAULT 'm²',
    PrecoPorUnidade DECIMAL(10, 2) NOT NULL DEFAULT 0.00,
    CHECK (UnidadeMedida IN ('m²', 'litros', 'quilos', 'unidades'))
);

-- Inserção de dados na tabela Materiais
INSERT INTO Materiais (Nome, Quantidade, UnidadeMedida, PrecoPorUnidade)
VALUES
('Cimento', 100, 'quilos', 25.00),
('Areia', 200, 'quilos', 15.50),
('Brita', 150, 'quilos', 18.00),
('Tijolo', 1000, 'unidades', 1.20),
('Cal', 50, 'quilos', 12.50);

-- Tabela EstoqueMateriais
CREATE TABLE IF NOT EXISTS EstoqueMateriais (
    id INT AUTO_INCREMENT PRIMARY KEY,
    NomeMaterial VARCHAR(255) NOT NULL,
    QuantidadeDisponivel DECIMAL(10, 2) NOT NULL
);

-- Inserção de dados na tabela EstoqueMateriais
INSERT INTO EstoqueMateriais (NomeMaterial, QuantidadeDisponivel)
VALUES
('Cimento', 500),
('Areia', 1000),
('Brita', 800),
('Tijolo', 3000),
('Cal', 150);

-- Tabela Orcamentos
CREATE TABLE IF NOT EXISTS Orcamentos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    SolicitacaoID INT NOT NULL,
    Detalhes VARCHAR(255) DEFAULT 'Em Análise',
    Total DECIMAL(10, 2) DEFAULT 0.00,
    OpcoesAlteracao VARCHAR(255) NOT NULL DEFAULT 'Nenhuma',
    FOREIGN KEY (SolicitacaoID) REFERENCES Solicitacoes(id),
    CHECK (OpcoesAlteracao IN ('Nenhuma', 'Solicitar Mudança', 'Aprovar'))
);

-- Inserção de dados na tabela Orcamentos
INSERT INTO Orcamentos (SolicitacaoID, Detalhes, Total, OpcoesAlteracao)
VALUES
(1, 'Orçamento inicial para casa de dois andares', 150000.00, 'Nenhuma'),
(2, 'Orçamento para construção de galpão pequeno', 250000.00, 'Solicitar Mudança'),
(3, 'Orçamento para fábrica de médio porte', 500000.00, 'Aprovar'),
(4, 'Orçamento para reforma de apartamento', 80000.00, 'Nenhuma'),
(5, 'Orçamento para construção de restaurante', 120000.00, 'Solicitar Mudança'),
(6, 'Orçamento para construção de casa moderna', 200000.00, 'Nenhuma'),
(7, 'Orçamento para loja de conveniência', 90000.00, 'Solicitar Mudança'),
(8, 'Orçamento para armazém logístico', 700000.00, 'Aprovar'),
(9, 'Orçamento para condomínio de luxo', 1000000.00, 'Nenhuma'),
(10, 'Orçamento para shopping center', 1500000.00, 'Solicitar Mudança'),
(11, 'Orçamento para usina de energia', 5000000.00, 'Nenhuma'),
(12, 'Orçamento para reforma de casa térrea', 75000.00, 'Solicitar Mudança'),
(13, 'Orçamento para centro de distribuição', 300000.00, 'Nenhuma'),
(14, 'Orçamento para linha de montagem', 1200000.00, 'Solicitar Mudança'),
(15, 'Orçamento para vila residencial', 800000.00, 'Aprovar'),
(16, 'Orçamento para restaurante temático', 150000.00, 'Nenhuma'),
(17, 'Orçamento para parque industrial', 2500000.00, 'Solicitar Mudança'),
(18, 'Orçamento para apartamento de luxo', 120000.00, 'Aprovar'),
(19, 'Orçamento para escritório corporativo', 450000.00, 'Nenhuma'),
(20, 'Orçamento para fábrica de eletrônicos', 1800000.00, 'Solicitar Mudança'),
(21, 'Orçamento para chalé de montanha', 90000.00, 'Nenhuma'),
(22, 'Orçamento para padaria artesanal', 80000.00, 'Solicitar Mudança'),
(23, 'Orçamento para refinaria', 6000000.00, 'Aprovar'),
(24, 'Orçamento para casa ecológica', 140000.00, 'Nenhuma'),
(25, 'Orçamento para centro comercial', 250000.00, 'Solicitar Mudança'),
(26, 'Orçamento para estúdio de fotografia', 50000.00, 'Aprovar'),
(27, 'Orçamento para fábrica de cimento', 3500000.00, 'Nenhuma'),
(28, 'Orçamento para coworking', 200000.00, 'Solicitar Mudança'),
(29, 'Orçamento para sobrado', 100000.00, 'Aprovar'),
(30, 'Orçamento para farmácia', 120000.00, 'Nenhuma'),
(31, 'Orçamento para unidade fabril', 2200000.00, 'Solicitar Mudança'),
(32, 'Orçamento para cobertura de luxo', 300000.00, 'Aprovar'),
(33, 'Orçamento para galeria de arte', 110000.00, 'Nenhuma'),
(34, 'Orçamento para central de reciclagem', 800000.00, 'Solicitar Mudança'),
(35, 'Orçamento para loft urbano', 60000.00, 'Aprovar');


-- Tabela Pagamentos
CREATE TABLE IF NOT EXISTS Pagamentos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    OrcamentoID INT NOT NULL,
    Valor DECIMAL(10, 2) DEFAULT 0.00,
    MetodoPagamento VARCHAR(50) NOT NULL DEFAULT 'Boleto',
    DataVencimento DATE DEFAULT NULL,
    FOREIGN KEY (OrcamentoID) REFERENCES Orcamentos(id),
    CHECK (MetodoPagamento IN ('Boleto', 'Cartão de Crédito', 'Pix'))
);

-- Inserção de dados na tabela Pagamentos
INSERT INTO Pagamentos (OrcamentoID, Valor, MetodoPagamento, DataVencimento)
VALUES
(1, 50000.00, 'Boleto', '2024-12-10'),
(2, 75000.00, 'Cartão de Crédito', '2024-12-15'),
(3, 150000.00, 'Pix', '2024-12-20'),
(4, 20000.00, 'Boleto', '2024-12-25'),
(5, 40000.00, 'Pix', '2024-12-30');
-- Tabela StatusEntrega
CREATE TABLE IF NOT EXISTS StatusEntrega (
    id INT AUTO_INCREMENT PRIMARY KEY,
    CodigoPedido VARCHAR(255) NOT NULL DEFAULT 'N/A',
    Status VARCHAR(50) NOT NULL DEFAULT 'Pendente',
    DataEstimadaEntrega DATE DEFAULT NULL,
    Rastreamento VARCHAR(255) DEFAULT 'Ver Detalhes',
    CHECK (Status IN ('Pendente', 'Em Trânsito', 'Entregue', 'Cancelado'))
);

-- Inserção de dados na tabela StatusEntrega
INSERT INTO StatusEntrega (CodigoPedido, Status, DataEstimadaEntrega, Rastreamento)
VALUES
('PED001', 'Pendente', '2024-12-12', 'Ver Detalhes'),
('PED002', 'Em Trânsito', '2024-12-15', 'Ver Detalhes'),
('PED003', 'Entregue', '2024-12-10', 'Ver Detalhes'),
('PED004', 'Cancelado', NULL, 'N/A'),
('PED005', 'Em Trânsito', '2024-12-20', 'Ver Detalhes');

-- Tabela TiposProdutos
CREATE TABLE IF NOT EXISTS TiposProdutos (
    id_tipo INT AUTO_INCREMENT PRIMARY KEY,
    nome_tipo VARCHAR(50) NOT NULL
);

-- Inserção de dados na tabela TiposProdutos
INSERT INTO TiposProdutos (nome_tipo)
VALUES
('Material de Construção'),
('Ferramentas'),
('Acabamentos'),
('Equipamentos de Segurança'),
('Outros');

-- Tabela UnidadesMedida
CREATE TABLE IF NOT EXISTS UnidadesMedida (
    id_unidade INT AUTO_INCREMENT PRIMARY KEY,
    unidade VARCHAR(20) NOT NULL
);

-- Inserção de dados na tabela UnidadesMedida
INSERT INTO UnidadesMedida (unidade)
VALUES
('m²'),
('litros'),
('quilos'),
('unidades');

-- Tabela Produtos
CREATE TABLE IF NOT EXISTS Produtos (
    id_produto INT AUTO_INCREMENT PRIMARY KEY,
    id_tipo INT NOT NULL,
    id_unidade INT NOT NULL,
    preco DECIMAL(10, 2) NOT NULL,
    confirmado BOOLEAN DEFAULT FALSE,
    data_cadastro TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (id_tipo) REFERENCES TiposProdutos(id_tipo),
    FOREIGN KEY (id_unidade) REFERENCES UnidadesMedida(id_unidade)
);

-- Inserção de dados na tabela Produtos
INSERT INTO Produtos (id_tipo, id_unidade, preco, confirmado)
VALUES
(1, 3, 25.00, TRUE),
(2, 4, 15.50, TRUE),
(3, 1, 30.00, FALSE),
(4, 4, 120.00, TRUE),
(5, 2, 50.00, TRUE);

-- Inserção de dados adicionais nas tabelas EstoqueMateriais e Produtos para complementar
INSERT INTO EstoqueMateriais (NomeMaterial, QuantidadeDisponivel)
VALUES
('Bloco de Concreto', 500),
('Vidro Temperado', 300),
('Cerâmica', 600),
('Tubulação PVC', 800);

-- Tabela de relação Produtos e Estoque (se necessário, para maior controle de rastreamento)
CREATE TABLE IF NOT EXISTS RelacaoProdutoEstoque (
    id_relacao INT AUTO_INCREMENT PRIMARY KEY,
    id_produto INT NOT NULL,
    id_estoque INT NOT NULL,
    FOREIGN KEY (id_produto) REFERENCES Produtos(id_produto),
    FOREIGN KEY (id_estoque) REFERENCES EstoqueMateriais(id)
);

-- Inserção para associar Produtos ao Estoque
INSERT INTO RelacaoProdutoEstoque (id_produto, id_estoque)
VALUES
(1, 1),
(2, 2),
(3, 3),
(4, 4);




-- Mensagem para validar
SELECT 'Banco de dados `dbSuaObraAqui` Seja Bem Vindo!';

--
-- alterando tabelas 
-- Alterando o nome e o e-mail do usuário
UPDATE usuarios
SET nome = ' Atualizado', email = 'emailatualizado@gmail.com'
WHERE id = 1;
--
-- Alterando a data de cadastro
UPDATE cadastro_usuario
SET data_cadastro = '2024-12-01 12:00:00'
WHERE id_cadastro = 1;


--
-- Alterando a pergunta e o passo a passo
UPDATE FAQs
SET pergunta = 'Como alterar meu e-mail?', 
    passo_a_passo = '1. Acesse sua conta. 2. Vá em configurações. 3. Atualize seu e-mail.'
WHERE id_faq = 1;


--
-- Alterando o resultado da tentativa
UPDATE TentativasFAQ
SET resultado = FALSE
WHERE id_tentativa = 1;


--
-- Alterando a descrição do problema e o status
UPDATE SolicitacoesSuporte
SET descricao_problema = 'Problema resolvido com sucesso.',
    status = 'Resolvido'
WHERE id_suporte = 1;


--
-- Alterando a análise e o status de resolvido
UPDATE AnalisesSuporte
SET descricao_analise = 'Erro identificado e corrigido.', 
    resolvido = TRUE
WHERE id_analise = 1;


--
-- Alterando a nota e o comentário
UPDATE Avaliacoes
SET nota = 5, comentario = 'Atendimento excelente, muito ágil.'
WHERE id_avaliacao = 1;


--
-- Alterando a descrição e a área total
UPDATE Solicitacoes
SET Descricao = 'Construção de uma casa moderna.', AreaTotal = 200.00
WHERE id = 1;


--
-- Alterando a quantidade e o preço por unidade
UPDATE Materiais
SET Quantidade = 120, PrecoPorUnidade = 27.50
WHERE id = 1;


--
-- Alterando a quantidade disponível
UPDATE EstoqueMateriais
SET QuantidadeDisponivel = 600
WHERE id = 1;


--
-- Alterando o total e a opção de alteração
UPDATE Orcamentos
SET Total = 55000.00, OpcoesAlteracao = 'Solicitar Mudança'
WHERE id = 1;


--
-- Alterando o valor e o método de pagamento
UPDATE Pagamentos
SET Valor = 52000.00, MetodoPagamento = 'Pix'
WHERE id = 1;


--
-- Alterando o status e a data estimada de entrega
UPDATE StatusEntrega
SET Status = 'Entregue', DataEstimadaEntrega = '2024-12-05'
WHERE id = 1;


--
-- Alterando o preço e o status de confirmação
UPDATE Produtos
SET preco = 28.00, confirmado = TRUE
WHERE id_produto = 1;


--
