
![license](https://img.shields.io/badge/license-MIT-green.svg?longCache=true&style=flat-square)

### Instalação

1. Faça o download dos arquivos.
2. Extraia o pacote e copie as pastas "assets" e "application" para o diretório do seu MapOS.
3. Execute o comando no terminal no diretório do seu MapOS `php index.php tools migrate` para criar as colunas na tabela `os`. Caso não consiga executar comandos no terminal utilize o SQL abaixo.
```
ALTER TABLE os
ADD COLUMN assClienteImg VARCHAR(50),
ADD COLUMN assClienteIp VARCHAR(20),
ADD COLUMN assClienteData DATETIME,
ADD COLUMN assTecnicoImg VARCHAR(50),
ADD COLUMN assTecnicoIp VARCHAR(20),
ADD COLUMN assTecnicoData DATETIME;
```