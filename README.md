### Houveram autualizações no Mapos que não permitem mais o uso dessa assinatura.
### NÃO INSTALEM
### Aguarde atualização

![license](https://img.shields.io/badge/license-MIT-green.svg?longCache=true&style=flat-square)

Desenvolvido para ser implementado no [<img src="https://raw.githubusercontent.com/RamonSilva20/mapos/master/assets/img/logo.png" alt="MapOS">](https://github.com/RamonSilva20/mapos)

### Instalação

1. Faça o download dos arquivos.
2. Extraia o pacote e copie as pastas "assets" e "application" para o diretório do seu MapOS.
3. Execute o comando no terminal no diretório onde fica o "index.php" do seu MapOS `php index.php tools migrate`. Caso não consiga executar comandos no terminal utilize os SQL abaixo.
```
ALTER TABLE `os`
ADD COLUMN `assClienteImg` LONGTEXT,
ADD COLUMN `assClienteIp` VARCHAR(20),
ADD COLUMN `assClienteData` DATETIME,
ADD COLUMN `assTecnicoImg` LONGTEXT,
ADD COLUMN `assTecnicoIp` VARCHAR(20),
ADD COLUMN `assTecnicoData` DATETIME;

ALTER TABLE `usuarios`
ADD COLUMN `assinaturaImg` LONGTEXT;

INSERT INTO `configuracoes` (`config`, `valor`) VALUES ('usar_assinatura', 1), ('status_assinatura', 'Aprovado')
```

### Utilização

#### 1. Em "Sistema" na aba "OS" aparecerá as opções da assinatura.
![Configurações da Assinatura](https://i.imgur.com/gnprb6l.png)

#### 2. Ao habilitar as assinaturas aparecerá para seu cliente o botão de assinar e autorizar a OS
![Botão de assinar no vizualizar OS](https://i.imgur.com/sK8VZfq.png)

#### 3. Ao clicar nesse botão o cliente é direcionado pra aba Assinatura onde deverá assinar e enviar a assinatura, alterando o Status da OS para o qual você escolheu nas configurações.
![Área de assinatura da OS](https://i.imgur.com/EOXoQ2g.png)

#### 4. Já na *Área de administração*, em Editar OS haverá uma aba "Assinatura". Se for a primeira vez que a *PESSOA LOGADA* assina uma OS, a assinatura dela é salva para ser usada em OSs futuras.
`A assinatura é sempre do usuário que está LOGADO e não do técnico que consta na OS.`
`O cliente também poderá assinar pela Área de admin para facilitar e não precisar fazer o Cliente abrir o sistema, logar pra assinar.`
![Aba Assinatura no Editar OS](https://i.imgur.com/J6zjr9r.png)
![Botões de Limpar e enviar assinaturas](https://i.imgur.com/v2d40iR.png)

#### 5. Se já tiver assinado outra OS e a assinatura já está salva, o botão exibido para assinatura do técnico será "Adicione sua assinatura".
![Botão Adicione sua assinatura](https://i.imgur.com/cfp6pyg.png)

### Exemplos
#### 1. Como aparece a assinaturas no Editar OS
![Assinatura no Editar OS](https://i.imgur.com/iT7O8sx.png)

#### 2. Assinaturas no imprimir
![Assinaturas no imprimir OS](https://i.imgur.com/EKckBlB.png)

### ATENÇÃO
#### Se o técnico quiser alterar a assinatura, vá ao Banco de dados e apague o conteúdo da coluna "assinaturaImg" da tabela de usuários daquele usuário. não apague a imagem da pasta pois é ela que aparecerá nas OS que ele já assinou. Assim como não é possível trocar assinatura em um documento de papel já assinado, no sistema não seria diferente.
![Apagar conteúdo do Banco](https://i.imgur.com/RiOeAw3.png)
