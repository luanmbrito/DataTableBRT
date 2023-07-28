# DataTableBRT

Esse plugin foi criado para criação de tabelas editaveis de forma dinamica.
Ele te da a possibilidade de criar tabelas em branco ou enviando um formato json para ele.

Como usar:

chame o script dentro do seu hmtl
```html
<script src="datatablebrt.js"></script>
```
após importar crie a tag script no final do seu html
```html
const table = new DataTableBRT('#table')
```
você pode passar o id ou a classe do elemento pai onde irá ser criado a tabela

agora você cria ou uma tabela em branco 
```html
table.createGridTable(param1,param2,{param3} /* opcional */)

// param1 : quantidade de linhas a serem criadas
// param2 : quantidade de colunas a serem criadas 
/* param3 : json com o estilo dos elementos 
{
	"table": "classe Tabela",
	"tr": "classe Tr",
	"td": "classe Td",
	"th": "classe Th"
}
*/
```

ou uma tabela ja preenchida em forma de json
O json pode ter a quantidade do cabeçalho e do dados que quiser
```html
table.createJSONTable({param1},{param2}/* opcional */,{param3}/* opcional */)

/* param1: json com o seguinte formato
{"header":["nome","sobrenome","endereco"],
 "data":[
		["john","doe","alguma rua"],
		["joana"," darc","algum lugar"]
	]
}

/* param2 : json com o estilo dos elementos 
	    "table": "classe Tabela",
            "tr": "classe Tr",
            "td": "classe Td",
            "th": "classe Th"
*/
// param3: {editable: true} 
```

Segue abaixo 2 exemplos de uso

#### Exemplo 1

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-9ndCyUaIbzAi2FUVXJi0CjmCapSmO7SnpJef0486qhLnuZ2cdeRhO02iuK6FUUVM" crossorigin="anonymous">
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js" integrity="sha384-geWF76RCwLtnZ8qwWowPQNguL3RmwHVBC9FhGdlKrxdiJJigb/j/68SIy3Te4Bkz" crossorigin="anonymous"></script>
    <title>Data TableBRT</title>
</head>
<body>

    <div id="table">
        
    </div>
</body>
<script>

</script>
<script src="datatablebrt.js"></script>
    
<script>
    const table = DataTableBRT("#table")
    table.createGridTable(2,2,{table:"table"})   
    
</script>
</html>
```

#### Exemplo 2

```html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-9ndCyUaIbzAi2FUVXJi0CjmCapSmO7SnpJef0486qhLnuZ2cdeRhO02iuK6FUUVM" crossorigin="anonymous">
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js" integrity="sha384-geWF76RCwLtnZ8qwWowPQNguL3RmwHVBC9FhGdlKrxdiJJigb/j/68SIy3Te4Bkz" crossorigin="anonymous"></script>
    <title>Data TableBRT</title>
</head>
<body>

    <div id="table">
        
    </div>
</body>
<script>

</script>
<script src="datatablebrt.js"></script>
    
<script>
    const table = DataTableBRT("#table")
    table.createJSONTable(
        {"header":["nome","sobrenome","endereco"],
          "data": [
                    ["john","doe","alguma rua"],
                    ["joana"," darc","algum lugar"]
                  ]
        },
        {table:"table"},
        {editable:true}
        )   
    
</script>
</html>

```
