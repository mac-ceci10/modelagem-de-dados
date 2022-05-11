<!-- Mark down
 o que é um .md arquivo?
Estes são arquivos de texto utilizadas como arquivos de documentação Markdown através dialetos da língua Markdown. MD arquivos são normalmente guardados em formato de texto simples, incluindo símbolos de texto em linha, definindo como um texto é formatado como os recortes, a sua formatação de tabela, fontes e cabeçalhos. Os sistemas de documentação HTML encontrar MD arquivos úteis, bem como o controle de versão de código fonte, porque o texto legível que são historicamente revista pode ser comparado com os arquivos MD Ao contrário dos arquivos binários que não podem ser comparados facilmente. MD arquivos também são criados com a finalidade de autoria documentação de texto simples para facilitar a conversão para HTML. Arquivos usando a extensão MD foram desenvolvidos por John Gruber e são usados ​​principalmente pelo programa Markdown a partir do site Daring Fireball. Os arquivos leia-me de um projeto criado por meio do sistema de controle de versão online chamado GitHub também usa um formato README.md muitas vezes. MD arquivos são categorizados como arquivos de desenvolvedores mais utilizados pelos Markdown, uma ótima ferramenta para converter arquivos de texto para versões HTML de modo que os usuários podem criar arquivos que são fáceis de ler e escrever.
como abrir uma .md arquivo?
Lançar uma .md arquivo, ou qualquer outro arquivo no seu PC, clicando duas vezes nele. Se suas associações de arquivos estão configurados corretamente, o aplicativo que está destinado a abrir o seu .md arquivo irá abri-lo. É possível que você pode precisar baixar ou comprar o aplicativo correto. Também é possível que você tenha o aplicativo correto no seu PC, mas .md arquivos ainda não estão associados com ele. Neste caso, quando você tenta abrir um .md arquivo, você pode dizer ao Windows qual a aplicação é o correto para esse arquivo. A partir de então, a abertura de uma .md arquivo irá abrir o aplicativo correto.
Clique aqui para corrigir erros de associação de arquivo .md
aplicativos que abrem uma .md arquivo
Microsoft Notepad
Notepad2
Apple TextEdit
Microsoft WordPad
uma palavra de advertência
Tenha cuidado para não renomear a extensão em .md arquivos, ou quaisquer outros arquivos. Isso não vai mudar o tipo de arquivo. Apenas software de conversão especial pode mudar um arquivo de um tipo de arquivo para outro.  -->

# Comandos SQL para modelagem física

## Criar banco de dados
CREATE DATABASE vendas_marcia CHARACTER SET utf8mb4;


## Entrar no BD criado
USE DATABASE vendas_marcia;

## Criar a tabela fabricante - dentro desses parâmetro entram os campos / colunas.
## tipo de dados, se é null, auto increment, e chave primária para que o valor seja único
CREATE TABLE fabricante(
    id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(45) NOT NULL
);

## Criar a tabela produto - dentro desses parâmetro entram os campos / colunas.
## PARA SER UMA CHAVE ESTRANGEIRA, fabricante_id, precisa ter uma ligação. Por enquanto é apenas um campo.
CREATE TABLE produto(
    id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(45) NOT NULL,
    preco DECIMAL(8,2) NOT NULL,
    quantidade SMALLINT NULL,
    descricao TEXT(1000) NOT NULL,
    fabricante_id INT NOT NULL
);


## Alterando a tabela para criar um relacionamento por meio da chave estrangeira
##     ADD CONSTRAINT - é como se fosse uma restrição.

ALTER TABLE produto
    ADD CONSTRAINT fk_produto_fabricante
    FOREIGN KEY (fabricante_id) REFERENCES fabricante(id);




